---
description: 測試操作條件的相關資訊，包括比較（而非空白）、範圍、規則運算式和字串比對。
title: 測試操作條件
uuid: 6a117569-1372-4095-972b-76289a45f19e
exl-id: 6c1f521b-a6b9-4bb7-bdfa-56c615b0c916
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 6%

---

# 測試操作條件{#test-operation-conditions}

測試操作條件的相關資訊，包括比較（而非空白）、範圍、規則運算式和字串比對。

* [比較](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac)
* [非空白](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)
* [Range](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1db31583bb09418b8f49481a897b08a6)
* [規則運算式](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-ae9c016502cb44128760c58f2d2d5297)
* [字串符合](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f)

## 比較 {#section-fb2bdb3838504099b324b9838cdeeaac}

[!DNL Compare]條件會比較字串或數值。 若要比較字串值，您可以指定是否應考慮大小寫。

下表說明[!DNL Compare]條件的參數：

<table id="table_05B1FBB2AED242D99081E62BE2FBEC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 區分大小寫 </td> 
   <td colname="col2">True 或 False. 僅當「類型」為<span class="wintitle"> LEXARICH</span>時使用。 如果設定為false，則大寫和小寫字母被視為相等。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。條件注意事項。 </td> 
   <td colname="col3"> 註解 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入A </td> 
   <td colname="col2"> 要比較的兩個值中的第一個。 此值表示條件中的左操作數。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入B </td> 
   <td colname="col2"> 要比較的兩個值中的第二個。 此值代表條件中的正確運算元。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>比較操作。 可用操作（及其含義）如下： 
     <ul id="ul_74F3C298E9CC4FE89897BA0052A9EB9F"> 
      <li id="li_1605FA73474E404A84056D40E7082623"> =或==（輸入A等於輸入B） </li> 
      <li id="li_F694A262ED7A4787B2A68B877339620C"> &lt;&gt; 或 !=（輸入A不等於輸入B） </li> 
      <li id="li_1A75437E23B64BEB92297E1C771092B0"> &lt;&gt; </li> 
      <li id="li_B80ED6BE9DEA41FE84BC6BA3B7759276"> &lt;&gt; </li> 
      <li id="li_93148F34065F489E8E198DFB9F9F0E70"> &gt;（輸入A大於輸入B） </li> 
      <li id="li_8A98EE9AED2445429805169040BB253D"> &gt;=（輸入A大於或等於輸入B） </li> 
     </ul> </p> </td> 
   <td colname="col3"> = </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 類型 </td> 
   <td colname="col2">要進行的比較類型。 可用類型有<span class="wintitle"> LEXARICH</span>、<span class="wintitle"> NUMERIC</span>和<span class="wintitle"> DATETIME</span>。 有關類型的說明，請參閱<a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a">測試操作的測試類型</a>。 </td> 
   <td colname="col3"> <span class="wintitle"> 辭彙</span> </td> 
  </tr> 
 </tbody> 
</table>

此示例使用[!DNL Compare]條件來定義[!DNL Log Entry Condition]。 當資料工作台伺服器讀取每個事件資料記錄時，會比較數值x-age和55。 如果對於給定的日誌條目，x-age小於或等於55，則日誌條目將包括在資料集構建過程中。

![](assets/cfg_Condition_CompareCondition.png)

## 非空{#section-1decb9d887894073a1b6b3d985729ac8}

[!DNL Not Empty]條件會檢查欄位，以查看其是否包含值或空白。 對於[!DNL Input]欄位的值不為空的任何日誌條目，都滿足此條件。

下表說明[!DNL Not Empty]條件的參數：

| 參數 | 說明 | 預設 |
|---|---|---|
| 註解 | 選填。條件注意事項。 | 註解 |
| 輸入 | 用於檢查內容的日誌條目中的欄位的名稱。 |  |

此示例將作為其輸入x-some-field並測試該欄位是否為空。 如果填入欄位，則符合條件。

![](assets/cfg_Condition_NotEmpty.png)

## Range {#section-1db31583bb09418b8f49481a897b08a6}

[!DNL Range]條件採用輸入欄位，並確定該欄位的值是否在給定的最小(Min)和最大(Max)參數值內（含）。

下表說明[!DNL Range]條件的參數：

<table id="table_1587D8D333804FC28024C0DFC2F2D4D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 區分大小寫 </td> 
   <td colname="col2">True 或 False. 僅當<span class="wintitle">類型</span>為<span class="wintitle"> LEXARICH</span>時使用。 如果設定為false，則大寫和小寫字母被視為相等。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。條件注意事項。 </td> 
   <td colname="col3"> 註解 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 要用作輸入的日誌條目中的欄位的名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小值 </td> 
   <td colname="col2"> <p>範圍下界。 </p> <p> 此參數的值必須是常值或字串——而非欄位名稱。 如果您使用此欄位的日期，您必須指定時區。 有關支援的時區縮寫的清單，請參閱<a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">時區代碼</a>。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大值 </td> 
   <td colname="col2"> <p>距離上限。 </p> <p> <p>注意：此參數的值必須是常值或字串——而非欄位名稱。 如果您使用此欄位的日期，您必須指定時區。 有關支援的時區縮寫的清單，請參閱<a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">時區代碼</a>。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 類型 </td> 
   <td colname="col2">要進行的比較類型。 可用類型有<span class="wintitle"> LEXARICH</span>、<span class="wintitle"> NUMERIC</span>和<span class="wintitle"> DATETIME</span>。 有關類型的說明，請參閱<a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a">測試操作的測試類型</a>。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此示例使用[!DNL Range]條件來定義[!DNL Log Entry Condition]。 當資料工作台伺服器讀取每個[!DNL event data]記錄時，會比較數值x-age和55。 如果對於給定的日誌條目，x-age至少為55，則日誌條目將包括在資料集構建過程中。 此示例執行與[!DNL Compare]條件示例相同的函式。 請參閱[比較](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac)。

>[!NOTE]
>
>如果「最小值」或「最大值」參數保留為空，則資料工作台伺服器會替換可用的最小或最大整數值。 最小值為零(0)，最大值為無窮大。

![](assets/cfg_Condition_RangeCondition.png)

## 規則運算式 {#section-ae9c016502cb44128760c58f2d2d5297}

[!DNL Regular Expression]條件測試使用規則運算式模式匹配（請參閱[規則運算式](../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)）來確定指定輸入欄位的值是否包含與「匹配」參數中指定的模式之一匹配的字串。

如果輸入是字串的向量，則測試只會使用向量中的第一個值。 [!DNL Regular Expression]條件會執行完整字串比較。 如果要識別子字串，您必須在「」前面加上「」。*」。

下表說明[!DNL Regular Expression]條件的參數：

<table id="table_0BF5F89F87C9493B8DABA97620074FAD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 區分大小寫 </td> 
   <td colname="col2"> True 或 False. 如果設定為false，則大寫和小寫字母被視為相等。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。條件注意事項。 </td> 
   <td colname="col3"> 註解 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 要用作輸入的日誌條目中的欄位的名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 符合 </td> 
   <td colname="col2"> <p>要與輸入欄位值匹配的規則運算式模式。 </p> <p> <b> 若要新增規則運算式模式</b> 
     <ol id="ol_6D6467FF74334DEA8E8625C3B155D11D"> 
      <li id="li_9E13A63558FF44749C2E49BD50B7F770">按一下右鍵<span class="uicontrol"> Matches</span>。 </li> 
      <li id="li_195A2F3B6B9442F5B1DACDE0FC96CE5C">按一下「新增<span class="uicontrol"></span> &gt; <span class="uicontrol">規則運算式</span>」。 </li> 
      <li id="li_225E98F8EF39426A9483B86EA2CFE6DF">在文字方塊中輸入所要的規則運算式。 </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例說明如何使用[!DNL Regular Expression]條件來比對從網站流量收集到的資料欄位。 僅當cs(referrer-query)欄位包含與規則運算式`campaign=C[1-9][0-9]{4}`相符的字串時，條件才會傳回true。 此規則運算式與包含`campaign=C12345`的任何字串匹配。 但是，模式與字串`campaign=C0123&`不符，因為`C`後面的第一個字元不在`1-9`範圍內。

![](assets/cfg_Condition_RegularExpression.png)

## 字串符合{#section-f8d132085c6b4500bfbe4515b848142f}

[!DNL String Match]條件會測試字串的等同性。 它將指定欄位作為輸入，並根據操作的「匹配」參數中指定的字串測試每個日誌條目中該欄位的值。 如果這些區分大小寫的比對字串中的任何一個與所提供的輸入欄位中的值相同，運算會傳回true。 如果[!DNL StringCondition]不含相符字串，則條件會傳回false。 如果輸入是字串的向量，則測試只會使用向量中的第一個值（字串）。

<table id="table_BD599BAA5DD54B278813B6C38AC8DE6B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 區分大小寫 </td> 
   <td colname="col2"> True 或 False. 如果設定為false，則大寫和小寫字母被視為相等。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。條件注意事項。 </td> 
   <td colname="col3"> 註解 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 要用作輸入的日誌條目中的欄位的名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 符合 </td> 
   <td colname="col2"> <p>要與輸入欄位值相符的字串。 </p> <p> <b>若要新增字串</b> 
     <ol id="ol_9E32218C771445D88357960475FAD6EB"> 
      <li id="li_A700747858D0470491783E9B3933DAFE">按一下右鍵<span class="uicontrol"> Matches</span>。 </li> 
      <li id="li_9D1A2462EA404B0F84426176737CAFED">按一下「新增<span class="uicontrol"></span> &gt; <span class="uicontrol">字串</span>」。 </li> 
      <li id="li_E84D2439B59548E5B1803C64A295A18E">在文字方塊中輸入所要的字串。 </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例使用從網站流量收集到的資料來說明[!DNL String Match]條件的使用。 條件會測試輸入欄位(cs-uri-stem)是否符合Matches參數中指定的兩個字串，如果欄位cs-uri-stem是精確字串[!DNL /navigation/footer.asp]或精確字串[!DNL /navigation/header.asp]，則會成功。

![](assets/cfg_Condition_StringMatch.png)
