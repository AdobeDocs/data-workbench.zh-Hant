---
description: 規則運算式用於所有Data Workbench搜尋欄位，包括查詢實體面板。
title: 規則運算式
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
exl-id: 75841a70-e78a-429b-b00d-ac107b7a87aa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 2%

---

# 規則運算式{#regular-expressions}

規則運算式用於所有Data Workbench搜尋欄位，包括查詢實體面板。

* [關於規則運算式](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [規則運算式術語](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [關於常值匹配](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [使用超字元](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [模式擷取](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## 關於規則運算式{#section-cc9dc7293bb04fc0b41fe8acdee708f0}

規則運算式是一種文字模式，由英數字元和稱為超字元的特殊字元組成，可定位模式並從文字中擷取子字串。 規則表達式在電腦寫程式中廣泛使用，是Perl等語言的一個組成部分。

為了識別和擷取複雜的字串模式，Data Workbench伺服器會在某些轉換和條件中使用規則運算式。 以下是規則運算式的簡短指南。

本附錄並非規則運算式的完整簡介。 一個特別好的參考是Jeffrey E. F. Friedl的《Mastering Rule Expressions, 2nd Edition *》出版物。*

## 規則運算式術語{#section-80b0d54f731e448391532ab3eb3c525c}

| 詞語 | 定義 |
|---|---|
| 常值 | 常值是我們在規則運算式中用來尋找特定字元順序的字元。 例如，要在[!DNL shop/products.html]中查找產品，字串產品是常值，或字串中正在查找的。 |
| 超字元 | 超字元是特殊字元，在規則運算式的上下文中具有唯一的解釋。 例如，句點(.) 是用於匹配任何字元的超字元。 |
| 逸出序列 | 逸出序列只是告訴規則運算式引擎，我們想將其中一個超字元當成文字使用的一種方式。 逸出序列一律以反斜線字元(`\`)開頭。 將反斜線（也是元字元）放在元字元前面，規則運算式引擎將逸出的元字元解譯為常值。 例如，如果要匹配超字元句點(`.`)，則需要使用轉義序列。 不過，若要比對字串168.196.0.11中的其中一個句號，您可以使用由反斜線和句號(`\.`)組成的規則運算式。 |
| 模式 | 這是規則運算式的簡稱。 從本質上說，規則運算式是您嘗試比對目標字串的模式。 |
| 目標字串 | 此詞指的是我們在中搜尋以找出所需模式的字串。 |

## 關於常值匹配{#section-ec4497e3160c47ba9b828d939761b3e0}

常值比對會取用不含任何逸出字元的常值字串，並查看目標字串，以查看它是否為目標字串的子字串。

在此範例中，您可了解常值比對的運作方式。 請考量從網站流量收集資料，且cs(referrer)欄位包含下列值的情況：

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

若要判斷反向連結是否代表點按其中一個廣告的使用者，您必須查看反向連結是否包含字串廣告。 您只需使用常值字串廣告來搜尋目標字串，並判斷是否使用廣告將流量路由至網站即可。 雖然這會符合目標字串，但會在兩個位置相符，因此不明確，可能導致誤判。

下列URL包含兩個不同位置的字串廣告：

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

因此，如果您嘗試判斷哪些工作階段是因特定廣告促銷活動而開始，單純使用文字廣告作為規則運算式顯然是不夠的。 將常值變更為&quot;ad=&quot;會消除此模糊性，並導致運算式只產生單一比對。 不過，即使這可能也不足以確保反向連結是廣告促銷活動的一部分。 請考量下列反向連結：

`http://www.xyz.com/hello.html?pad=something`

您無法控制其他人用來建立網站連結的URL。 文字比對的機制太簡單，無法定位因廣告促銷活動而開始的工作階段。 以下章節探討如何使用超字元來進行更有彈性且功能強大的比對。

## 使用超字元{#section-e29a804336304ea1ba33d40d60139aa2}

超字元是程式或資料欄位中的特殊字元，提供其他字元的相關資訊。

| 元字元 | 說明 |
|---|---|
| . （圓點） | 比對單一字元，例如：`re:x.z`符合「xyz」或「xxz」。 |
| *（星號） | 匹配一個或多個字元，例如：`re:Z*`符合&quot;ZZZ&quot;。 |
| ? （萬用字元） | 匹配以前表達式的0或1以強制最小匹配，例如：`xy?z`符合&quot;xy&quot;和&quot;xyz&quot;。 |

其他常用規則運算式也可用來建立更複雜的搜尋字串。

**清單、範圍和OR**

常值比對可讓您尋找單一字串，但方括弧、破折號和垂直號可讓您定義目標字串中要尋找的項目清單。

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對於這個超字元…… </th> 
   <th colname="col2" class="entry"> 規則運算式處理器將…… </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 方括弧([ ]) </td> 
   <td colname="col2"> 將括弧內的任何字元與單個字元位置匹配。 例如，[AB]是指令，用來比對字母A或字母B，而[0123456789]表示符合0到9範圍內的任何字元。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 破折號(-) </td> 
   <td colname="col2"> <p>匹配字元範圍。 因此，我們不必寫[0123456789]，而只能寫[0-9]。 </p> <p> 這可擴充至一組方括弧內的字元範圍和多個範圍。 例如，[0-9A-C]匹配字元0到9以及A到C。 </p> <p> <p>注意： 若要測試破折號(-)，將其作為方括弧內的文字，必須排在第一或最後。 例如，針對 — 和0到9的[-0-9]測試。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 直立線符號 (|) </td> 
   <td colname="col2"> 將兩個選項之一與指定的目標字串匹配。 例如， b|nat會比對bat或nat。 </td> 
  </tr> 
 </tbody> 
</table>

考量下列範例:

| 模式 | 字串 | 符合 |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| 課程`[A-Z]` | 課程a | 無相符項目，因為小寫a不在大寫A到Z的範圍內。 |

**否定**

否定是表示您想要比對任何指定字元以外的項目的方式。 否定超字元(抑揚符號或脫字元號(`^`))是方括弧內的第一個字元，用來表示您希望比對是方括弧中除了其餘字元以外的任何字元。 例如，若要比對除分號(`;`)以外的任何字元，您可以寫入

[`^;`]

這會比對除分號以外的任何字元。

**定位**

若要強制比對目標字串的開頭或結尾，會使用兩個超字元之一。

| 對於這個超字元…… | 規則運算式處理器將…… |
|---|---|
| 抑揚符號或脫字元號(`^`) | 比對字串的開頭。 例如，^`[Tt]`他會符合目標字串&quot;The Being&quot;，但不符合&quot;This is the being&quot;。 |
| 貨幣符號 (`$`) | 比對字串的結尾。 例如，`[Ee]`nd$會符合「This is end」，但不符合「The end is a special time」。 |

>[!NOTE]
>
>如果規則運算式開頭包含^，結尾包含$，則整個目標字串必須符合規則運算式。

**匹配任何內容**

期間(.) 是特殊的超字元，會比對目標字串中的任何字元。 例如，規則運算式`^…$`符合任何長度正好為三個字元的目標字串。 規則運算式「……」會匹配任何至少包含三個字元的目標字串。

**重複模式**

迭代超字元可讓您多次匹配模式。

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對於這個超字元…… </th> 
   <th colname="col2" class="entry"> 規則運算式處理器將…… </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 問號(?) </td> 
   <td colname="col2"> 不匹配元字元(?)前面緊鄰的字元的實例或實例。 例如，模式rea?d會比對紅色和讀取。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 星號 (*) </td> 
   <td colname="col2"> 匹配超字元(*)前面的零個或多個字元。 例如，模式[0-9]*匹配任意數字0到9（任意整數）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plus (+) </td> 
   <td colname="col2"> 匹配前面字元或範圍的一個或多個出現次數。 例如，模式thre+會比對三個，但不符合。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>匹配正在處理的字元或範圍n次。 以下模式與美國電話號碼相符：<code>[0-9]{3}-[0-9]{3}-[0-9]{4}</code>。 </p> <p> 雖然不是最佳模式，但會決定目標字串是否為正確格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> 至少匹配n次，最多匹配m次。 例如，fo{1,2}d將匹配fod和food，但不匹配food。 </td> 
  </tr> 
 </tbody> 
</table>

## 模式提取{#section-4389779653b64f6cb7c47615b25c1a79}

模式比對只是規則運算式的一部分。 規則運算式也提供用於擷取目標字串關鍵部分的機制。 這需使用左括弧和右括弧來完成。 這些提取通常用作輸入到另一個進程，並通過使用&#x200B;*%position%*&#x200B;進行訪問，其中position是一個整數，引用哪組括弧匹配。

請考量下列模式擷取範例：

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
   <td colname="col4"> <p>%1% =贏 </p> <p> %2% = 98 </p> </td> 
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
   <td colname="col3"> 不匹配，因為小寫a不在大寫A到Z的範圍內 </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>
