---
description: 規則運算式會用於所有資料工作台搜尋欄位，包括查詢實體面板。
solution: Analytics
title: 規則運算式
topic: Data workbench
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
translation-type: tm+mt
source-git-commit: 0727e5b18c89a22b6ee775b1293d3b68e5cee81c
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 2%

---


# 規則運算式{#regular-expressions}

規則運算式會用於所有資料工作台搜尋欄位，包括查詢實體面板。

* [關於規則運算式](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [規則運算式術語](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [關於常值匹配](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [使用元字元](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [圖樣擷取](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## 關於規則運算式 {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

規則運算式是文字模式，由字母數字字元和稱為元字元的特殊字元組合組成，可找出模式並從文字擷取子字串。 規則表達式在電腦寫程式中廣泛使用，是Perl等語言的一個組成部分。

為了識別和提取複雜的字串模式，資料工作台伺服器在某些轉換和條件中使用規則運算式。 以下是規則運算式的簡要指南。

本附錄不是規則運算式的完整簡介。 O&#39;Reilly出版物Mastering Regular Expressions, *2nd Edition* ，作者Jeffrey E特別好。F.弗里德爾。

## 規則運算式術語 {#section-80b0d54f731e448391532ab3eb3c525c}

| 詞語 | 定義 |
|---|---|
| 常值 | 常值是我們在規則運算式中使用的字元，用以找出特定的字元序列。 例如，若要在中尋找產 [!DNL shop/products.html]品，字串產品是常值，或我們在字串中尋找的。 |
| 元字元 | 元字元是特殊字元，在規則運算式的上下文中具有唯一的解譯。 例如，句點(.) 是用於匹配任何字元的元字元。 |
| 逸出序列 | 逸出序列只是告訴規則運算式引擎我們想使用其中一個元字元作為常值。 逸出序列一律以反斜線字元(`\`)開頭。 將反斜線（也是元字元）放在元字元前面，規則運算式引擎會將逸出的元字元解譯為常值。 例如，如果要匹配元字元句點(`.`)，則需要使用轉義序列。 不過，若要比對字串168.196.0.11中的其中一個句點，您可以使用由反斜線和句點(`\.`)組成的規則運算式。 |
| 模式 | 這是規則運算式的簡稱。 實際上，規則運算式是您嘗試比對目標字串的模式。 |
| 目標字串 | 此術語是指我們正在搜尋的字串，以找出所要的模式。 |

## 關於常值匹配 {#section-ec4497e3160c47ba9b828d939761b3e0}

常值比對會擷取不含任何逸出字元的常值字串，並在目標字串中尋找，以查看它是否為目標字串的子字串。

在此範例中，您會看到常值比對的運作方式。 請考慮從網站流量收集資料，而cs(referrer)欄位包含下列值的情況：

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

若要判斷反向連結是否代表點按其中一個廣告的訪客，您需要查看反向連結是否包含字串廣告。 您只需使用常值字串廣告來搜尋目標字串，並判斷廣告是否用於將流量路由至網站。 雖然這會符合目標字串，但會在兩個位置符合，因此不明確，並可能導致誤報。

下列URL包含兩個不同位置的字串廣告：

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

因此，如果您嘗試判斷哪些作業是由特定廣告促銷活動所啟動，僅使用常值廣告作為規則運算式顯然是不夠的。 將常值變更為&quot;ad=&quot;會消除此模糊性，並導致運算式只進行單一比對。 不過，即使這也不足以確保反向連結是廣告促銷活動的一部分。 請考慮下列反向連結：

`http://www.xyz.com/hello.html?pad=something`

您無法控制其他人用來建立網站連結的URL。 常值比對機制過於簡單，無法找出因廣告促銷活動而啟動的工作階段。 下節將討論如何使用元字元來進行更有彈性且功能強大的比對。

## 使用元字元 {#section-e29a804336304ea1ba33d40d60139aa2}

元字元是程式或資料欄位中的一個特殊字元，它提供了有關其他字元的資訊。

| 元字元 | 描述 |
|---|---|
| . （點） | 符合單一字元，例如： `re:x.z` 匹配&quot;xyz&quot;或&quot;xxz&quot;。 |
| *（星號） | 匹配一個或多個字元，例如： `re:Z*` 匹配&quot;ZZZ&quot;。 |
| ? （萬用字元） | 匹配上一個表達式的0或1以強制最小匹配，例如： `xy?z` 匹配&quot;xy&quot;和&quot;xyz&quot;。 |

其他常用規則運算式也可用來建立更複雜的搜尋字串。

**清單、範圍和OR**

常值比對可讓您尋找單一字串，但方括弧、破折號和垂直線可讓您定義目標字串中要尋找的項目清單。

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對於這個元字元…… </th> 
   <th colname="col2" class="entry"> 規則運算式處理器將…… </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 方括弧([ ]) </td> 
   <td colname="col2"> 使用單一字元位置比對方括弧內的任何字元。 例如，[AB]是指令，用於比對字母A或字母B，以及[0123456789]（與0到9範圍內的任何字元相符）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 破折號(-) </td> 
   <td colname="col2"> <p>比對字元範圍。 因此，我們可以直接寫[0-9]，而不是寫[0123456789]。 </p> <p> 這可延伸至一組方括弧內的字元範圍和多個範圍。 例如，[0-9A-C]與字元0至9以及A至C相符。 </p> <p> <p>注意： 若要測試破折號(-)在方括弧內的文字，它必須是第一個或最後一個。 例如，[-0-9]測試——和0至9。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 直立線符號 (|) </td> 
   <td colname="col2"> 將兩個選項之一比對給定目標字串。 例如， b|nat與bat或nat匹配。 </td> 
  </tr> 
 </tbody> 
</table>

考量下列範例:

| 模式 | 字串 | 符合 |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| 課程`[A-Z]` | 課程a | 不匹配，因為下殼a不在上殼A到Z的範圍內。 |

**否定**

否定是表示您想要比對除指定字元以外的任何項目的方式。 否定元字元(抑揚符號或脫字元號`^`)是方括弧內的第一個字元，用來表示您希望比對除方括弧內的其餘字元以外的任何字元。 例如，若要比對除分號(`;`)以外的任何字元，您會

[`^;`]

這會比對除分號以外的任何字元。

**定位**

若要強制比對目標字串的開始或結尾，會使用兩個元字元中的一個。

| 對於這個元字元…… | 規則運算式處理器將…… |
|---|---|
| 抑揚符號(`^`) | 比對字串的開頭。 例如，^`[Tt]`他會比對目標字串&quot;The Beging&quot;，但不會比對&quot;This is the starting&quot;。 |
| 貨幣符號 (`$`) | 比對字串結尾。 例如， `[Ee]`nd$會比對「This is the end」，但不會比對「The end is a special time」。 |

>[!NOTE]
>
>當規則運算式在開頭包含^和結尾包含$時，整個目標字串必須符合規則運算式。

**匹配任何內容**

句號(.) 是與目標字串中任何字元相符的特殊元字元。 例如，規則運算式會 `^…$` 比對任何三個字元長度剛好的目標字串。 規則運算式&quot;。..&quot;與包含至少三個字元的任何目標字串相符。

**重複的圖樣**

小版本元字元可讓您多次比對陣列。

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對於這個元字元…… </th> 
   <th colname="col2" class="entry"> 規則運算式處理器將…… </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 問號(?) </td> 
   <td colname="col2"> 不匹配元字元(?)前方的例項或一個字元例項。 例如，模式rea?d與red和read匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 星號 (*) </td> 
   <td colname="col2"> 比對緊接在元字元(*)之前的零個或多個字元。 例如，模式[0-9]*與任意數字的0到9（任意整數）匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plus (+) </td> 
   <td colname="col2"> 比對一或多個前面的字元或範圍。 例如，模式ther+會比對3個，但不會比對到。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>正確匹配n次繼續字元或範圍。 下列模式符合美國電話號碼： <code>[0-9]{3}-[0-9]{3}-[0-9]{4}</code>. </p> <p> 雖然不是最佳模式，但它會決定目標字串是否為正確格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> 至少匹配n次以上字元，最多匹配m次。 例如，fo{1,2}d會比對食物和食物，但不會比對食物。 </td> 
  </tr> 
 </tbody> 
</table>

## 圖樣擷取 {#section-4389779653b64f6cb7c47615b25c1a79}

模式匹配只是規則運算式功能的一部分。 規則運算式也提供擷取目標字串關鍵部分的機制。 這是使用左括弧和右括弧來完成的。 這些提取通常用作輸入到另一個進程中，並通過使用 *%position%*（其中position是一個整數，指的是哪組括弧已匹配的計數）來訪問。

請考慮下列模式擷取範例：

<table id="table_BC8D471B966844049FFFCDEC0F183941"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 模式 </th> 
   <th colname="col2" class="entry"> 字串 </th> 
   <th colname="col3" class="entry"> 符合 </th> 
   <th colname="col4" class="entry"> 提取 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Win(9[58]) </td> 
   <td colname="col2"> OS=Win95 </td> 
   <td colname="col3"> Win95 </td> 
   <td colname="col4"> %1% = 95 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> (Win)(95|8) </td> 
   <td colname="col2"> OS=Win98 </td> 
   <td colname="col3"> Win98 </td> 
   <td colname="col4"> <p>%1% = Win </p> <p> %2% = 98 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mozilla/([0-9])。([0-9]) </td> 
   <td colname="col2"> Mozilla/3.0 </td> 
   <td colname="col3"> Mozilla/3.03 </td> 
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 課程([A-Z]) </td> 
   <td colname="col2"> 課程a </td> 
   <td colname="col3"> 不匹配，因為下殼a不在上殼A到Z的範圍內 </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>

