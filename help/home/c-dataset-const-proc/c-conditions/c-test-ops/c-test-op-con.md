---
description: 測試操作條件的相關資訊，包括比較（而非空白）、範圍、規則運算式和字串比對。
solution: Analytics
title: 測試操作條件
topic: Data workbench
uuid: 6a117569-1372-4095-972b-76289a45f19e
translation-type: tm+mt
source-git-commit: 0727e5b18c89a22b6ee775b1293d3b68e5cee81c
workflow-type: tm+mt
source-wordcount: '1119'
ht-degree: 6%

---


# 測試操作條件{#test-operation-conditions}

測試操作條件的相關資訊，包括比較（而非空白）、範圍、規則運算式和字串比對。

* [比較](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac)
* [非空白](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)
* [範圍](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1db31583bb09418b8f49481a897b08a6)
* [規則運算式](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-ae9c016502cb44128760c58f2d2d5297)
* [字串符合](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f)

## 比較 {#section-fb2bdb3838504099b324b9838cdeeaac}

條件 [!DNL Compare] 會比較字串或數值。 若要比較字串值，您可以指定是否應考慮大小寫。

下表說明 [!DNL Compare] 了該條件的參數：

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
   <td colname="col2">True 或 False. 僅在「類型」為「詞法」時 <span class="wintitle"> 使用</span>。 如果設定為false，則大寫和小寫字母被視為相等。 </td> 
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
      <li id="li_1A75437E23B64BEB92297E1C771092B0"> &lt;（輸入A小於輸入B） </li> 
      <li id="li_B80ED6BE9DEA41FE84BC6BA3B7759276"> &lt;=（輸入A小於或等於輸入B） </li> 
      <li id="li_93148F34065F489E8E198DFB9F9F0E70"> &gt;（輸入A大於輸入B） </li> 
      <li id="li_8A98EE9AED2445429805169040BB253D"> &gt;=（輸入A大於或等於輸入B） </li> 
     </ul> </p> </td> 
   <td colname="col3"> = </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 類型 </td> 
   <td colname="col2">要進行的比較類型。 可用類型 <span class="wintitle"> 有</span>XELICHARG <span class="wintitle"> 、NUMERIC</span>和 <span class="wintitle"> DATETIME</span>。 有關類型的說明，請參 <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> 閱測試操作的測試類型</a>。 </td> 
   <td colname="col3"> <span class="wintitle"> 辭彙</span> </td> 
  </tr> 
 </tbody> 
</table>

此示例使用 [!DNL Compare] 條件來定義 [!DNL Log Entry Condition]。 當資料工作台伺服器讀取每個事件資料記錄時，會比較數值x-age和55。 如果對於給定的日誌條目，x-age小於或等於55，則日誌條目將包括在資料集構建過程中。

![](assets/cfg_Condition_CompareCondition.png)

## 非空白 {#section-1decb9d887894073a1b6b3d985729ac8}

條 [!DNL Not Empty] 件會檢查欄位，以查看其是否包含值或空白。 對於欄位值不為空的任何日誌條目，都 [!DNL Input] 滿足此條件。

下表說明 [!DNL Not Empty] 了該條件的參數：

| 參數 | 說明 | 預設 |
|---|---|---|
| 註解 | 選填。條件注意事項。 | 註解 |
| 輸入 | 用於檢查內容的日誌條目中的欄位的名稱。 |  |

此示例將作為其輸入x-some-field並測試該欄位是否為空。 如果填入欄位，則符合條件。

![](assets/cfg_Condition_NotEmpty.png)

## 範圍 {#section-1db31583bb09418b8f49481a897b08a6}

條 [!DNL Range] 件採用輸入欄位並確定該欄位的值是否落在給定的最小(Min)和最大(Max)參數值內，包括。

下表說明 [!DNL Range] 了該條件的參數：

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
   <td colname="col2">True 或 False. 僅當「類型」為 <span class="wintitle"> LEXARICH</span><span class="wintitle"> 時使用</span>。 如果設定為false，則大寫和小寫字母被視為相等。 </td> 
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
   <td colname="col2"> <p>範圍下界。 </p> <p> 此參數的值必須是常值或字串——而非欄位名稱。 如果您使用此欄位的日期，您必須指定時區。 如需支援的時區縮寫清單，請參閱時 <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 區代碼</a>。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大值 </td> 
   <td colname="col2"> <p>距離上限。 </p> <p> <p>注意：此參數的值必須是常值或字串——而非欄位名稱。 如果您使用此欄位的日期，您必須指定時區。 如需支援的時區縮寫清單，請參閱時 <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 區代碼</a>。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 類型 </td> 
   <td colname="col2">要進行的比較類型。 可用類型 <span class="wintitle"> 有</span>XELICHARG <span class="wintitle"> 、NUMERIC</span>和 <span class="wintitle"> DATETIME</span>。 有關類型的說明，請參 <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> 閱測試操作的測試類型</a>。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此示例使用 [!DNL Range] 條件來定義 [!DNL Log Entry Condition]。 當資料工作台伺服器讀取每 [!DNL event data] 個記錄時，會比較數值x-age和55。 如果對於給定的日誌條目，x-age至少為55，則日誌條目將包括在資料集構建過程中。 此示例執行與條件示例相同 [!DNL Compare] 的函式。 請參 [閱比較](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac)。

>[!NOTE]
>
>如果「最小值」或「最大值」參數保留為空，則資料工作台伺服器會替換可用的最小或最大整數值。 最小值為零(0)，最大值為無窮大。

![](assets/cfg_Condition_RangeCondition.png)

## 規則運算式 {#section-ae9c016502cb44128760c58f2d2d5297}

條件 [!DNL Regular Expression] 測試使用規則運算式模式比對(請參閱 [Regular Expressions](../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c))來判斷指定輸入欄位的值是否包含符合Matches參數中指定其中一個模式的字串。

如果輸入是字串的向量，則測試只會使用向量中的第一個值。 該條 [!DNL Regular Expression] 件會執行完整字串比較。 如果要識別子字串，您必須在「」前面加上「」。*」。

下表說明 [!DNL Regular Expression] 了該條件的參數：

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
      <li id="li_9E13A63558FF44749C2E49BD50B7F770">以滑鼠右鍵按一 <span class="uicontrol"> 下「符合</span>」。 </li> 
      <li id="li_195A2F3B6B9442F5B1DACDE0FC96CE5C">按一 <span class="uicontrol"> 下「新增</span> &gt;規則 <span class="uicontrol"> 運算式」</span>。 </li> 
      <li id="li_225E98F8EF39426A9483B86EA2CFE6DF">在文字方塊中輸入所要的規則運算式。 </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例說明如何使用條 [!DNL Regular Expression] 件來比對從網站流量收集到的資料欄位。 僅當cs(referrer-query)欄位包含與規則運算式相符的字串時，條件才會傳回true `campaign=C[1-9][0-9]{4}`。 此規則運算式與包含&quot;campaign=C12345&quot;的任何字串相符。 但是，模式不符合字串&quot;campaign=C0123&amp;&quot;，因為&quot;C&quot;後的第一個字元不在1-9範圍內。

![](assets/cfg_Condition_RegularExpression.png)

## 字串符合 {#section-f8d132085c6b4500bfbe4515b848142f}

條件 [!DNL String Match] 會測試字串等式。 它將指定欄位作為輸入，並根據操作的「匹配」參數中指定的字串測試每個日誌條目中該欄位的值。 如果這些區分大小寫的比對字串中的任何一個與所提供的輸入欄位中的值相同，運算會傳回true。 若條件不含 [!DNL StringCondition] 相符字串，則傳回false。 如果輸入是字串的向量，則測試只會使用向量中的第一個值（字串）。

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
      <li id="li_A700747858D0470491783E9B3933DAFE">以滑鼠右鍵按一 <span class="uicontrol"> 下「符合</span>」。 </li> 
      <li id="li_9D1A2462EA404B0F84426176737CAFED">Click <span class="uicontrol"> Add new</span> &gt; <span class="uicontrol"> String</span>. </li> 
      <li id="li_E84D2439B59548E5B1803C64A295A18E">在文字方塊中輸入所要的字串。 </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例使用從網站流量收集到的資料來說明該條件的使 [!DNL String Match] 用。 條件會測試輸入欄位(cs-uri-stem)是否符合Matches參數中指定的兩個字串，如果欄位cs-uri-stem是精確字串或精確字串，則 [!DNL /navigation/footer.asp] 會成功 [!DNL /navigation/header.asp]。

![](assets/cfg_Condition_StringMatch.png)

