---
description: 定義目標、假設和實驗詳細資訊並建立test內容後，必須配置感測器以部署受控實驗。
solution: Analytics
title: 設定和部署實驗
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
exl-id: 957c2ea2-72a5-4bb2-af1d-65187613c26d
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# 設定和部署實驗{#configuring-and-deploying-the-experiment}

定義目標、假設和實驗詳細資訊並建立test內容後，必須配置感測器以部署受控實驗。

## 配置實驗配置檔案 {#section-037fe7dea9c94aee9cdc354dafdb7c03}

要配置實驗，必須完成由Adobe(名為 [!DNL TestExperiment.xls] )。 此檔案配置 [!DNL Sensor] 執行實驗，並且是您在中指定的文本檔案的Excel版本 [修改ExpFile參數](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

此檔案可以包含有關多個實驗的資訊，這些實驗可以在相同或不同的時間運行，並使用不同的組和百分比，但這些實驗不以任何方式關聯。

用戶將被置於組中，用於配置為此時正在運行的檔案中列出的每個實驗。

>[!NOTE]
>
>每個實驗都與其他實驗無關。 對一個實驗所做的更改不會影響任何其他實驗，儘管訪問者可能在多個實驗中，但結果之間並不相關。 如果您認為多個實驗中的更改之間存在關聯，則必須建立一個新實驗，將這些更改test在一起。

**配置實驗**

應在實驗開始之前完成此檔案，而不是在實驗運行期間修改資訊。

>[!NOTE]
>
>如果實驗開始後實驗的定義發生變化，任何實驗都會立即失效。

1. 如果您對Web或應用程式伺服器具有管理員訪問權限，請導航到 [!DNL Sensor] 安裝資料夾 [!DNL Sensor] 訪問Web群集中的電腦 [!DNL TestExperiment.xls] 的子菜單。 如果您沒有管理員訪問權限，請與Adobe客戶經理聯繫以請求 [!DNL TestExperiment.xls] 的子菜單。

1. 開啟 [!DNL TestExperiment.xls] 檔案（如果需要，可以更名此檔案）並填寫以下欄位：

<table id="table_FDD6AE631C614F97AD7AE8829E53CCAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 實驗 </td> 
   <td colname="col2"> <p>實驗的描述性名稱。 每個實驗名稱必須唯一，且不能包含空格。 </p> <p>在顯示實驗結果時，使用實驗名稱。 <span class="keyword"> 洞察力 </span>。 這些名稱將作為受控實驗尺寸中的元素名稱的前半部分出現。 元素名稱的後半部分是此檔案中「組」欄位中的組名稱。 每個組都使用實驗名稱后跟組名稱的下列格式命名： </p> <p><i>EmperityName.Group名稱</i> </p> <p>例如： <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 開始 </td> 
   <td colname="col2"> <p>希望實驗開始的日期和時間。 如果不輸入值，則在部署檔案後立即開始實驗。 </p> <p>格式：MM/DD/YYYY H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">如果將開始時間和停止時間留空，則實驗將無限期運行。 </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">可以提前預定開始和停止時間；因此，如果需要，您可以同時配置下一年的所有實驗。 </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">啟動和停止時間基於Web伺服器的系統時間。 如果時鐘因任何原因而改變，則您的實驗可能會意外啟動或停止。 </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">如果希望將實驗添加為配置檔案條目，但不希望該實驗在不久的將來運行，則可以使用數字元號「#」注釋掉實驗資訊，或定義過去的開始和停止時間。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop </td> 
   <td colname="col2"> <p>希望實驗結束的日期和時間。 當停止日期和時間出現時， <span class="wintitle"> 感測器 </span> 將停止將標識為test組的cookie值發送到testURI，並將將所有cookie發送到控制組URI。 </p> <p>格式：MM/DD/YYYY H:MM </p> <p>請參閱 <span class="wintitle"> 開始 </span> 的子菜單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 群組 </td> 
   <td colname="col2"> <p>實驗中每組訪問者的描述性名稱。 組名稱不能包含空格。 </p> <p>在中顯示實驗結果時使用組名 <span class="keyword"> 洞察力 </span>。 有關詳細資訊，請參閱「實驗」欄位說明。 </p> <p>可以根據在「百分比」(Percentage)欄位中輸入的值隱式或顯式定義控制組。 </p> <p> <p>注：為了滿足在定義的時間段內需要的訪問者數量，以便實驗在統計上有效，您可能需要降低置信度或增加時間段。 例如，如果您的時間框為5天，您的置信度為98%，並且您需要的訪問者數量超過了該時段的預期數量，則您需要增加該時段或降低置信度，直到預期訪問者數量超過運行統計有效實驗所需的數量。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 百分比 </td> 
   <td colname="col2"> <p>要包括在每個定義組中的網站訪問者百分比。 這些值可以表示為百分比或小數值。 此外，這兩個值必須大於或小於一個。 </p> <p>例如： </p> <p>33.3%和66.7% </p> <p>.99和。01 </p> <p>如果所有組的總和小於100，則未定義的超額將預設為控制組。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 原始URL </td> 
   <td colname="col2"> <p>要重新映射的內容的URI，後跟$。 此值區分大小寫。 </p> <p>格式：index.asp$ </p> <p>可以使用URI末尾的美元符號($)指定原始URI，以表示需要與檔案名完全匹配。 例如，表達式 <span class="filepath"> /product/product_view.asp$ </span> 僅與同一頁匹配，而 <span class="filepath"> /product </span> 與中的任何頁面匹配 <span class="filepath"> /product </span> 目錄，可用於重新映射整個子樹。 實驗將忽略未在檔案名末尾指定$字元的原始URL條目，除非ExpPartialMatch參數已設定為「on」。 有關此參數的詳細資訊，請參見 <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> 修改ExpPartialMatch參數（可選） </a>。 </p> <p>受控實驗功能忽略附加到URI乾的任何查詢字串。 例如， </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982 </span> 不是有效的URI，但該頁 <span class="filepath"> /product/product_view.asp </span> 是有效的URI。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重新映射的URL </td> 
   <td colname="col2"> <p>備用內容的URI。 </p> <p>格式：索引2.asp </p> <p>請參閱「原始URL」欄位的注釋。 </p> </td> 
  </tr> 
 </tbody> 
</table>

以下是已完成的示例 [!DNL TextExperiment.xls] 電子錶格：

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>不要修改電子錶格中的列位置。

此示例表示，「New_Homepage」實驗從2006年6月1日開始，到2006年6月30日結束，包含包含50%訪問者的控制組和包含50%訪問者的test組，這些訪問者查看一個URI的不同內容。

>[!NOTE]
>
>儘管上面的示例檔案定義了顯式控制組，但不必顯式定義控制組 — 實驗會自動建立控制組。 如果實驗中所有組的百分比之和小於100%，則向不屬於其中一個顯式組的用戶分配隱式控制組。

1. 要插入注釋以提供有關特定實驗的其他資訊，請用數字元號(#)開始單元格，然後按照注釋進行操作。 注釋可以插入檔案中的任意位置。
1. 在實驗配置電子錶格中完成變數後，保存更改，然後以制表符分隔的文本格式( [!DNL *.txt])，使用在 [!DNL Sensor] 配置檔案。 請參閱 [修改ExpFile參數](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

   以下是實驗配置文本檔案的示例：

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >由於此檔案中需要的頁籤，因此不要手動編輯實驗配置文本檔案。 如果需要對檔案進行更改，請在實驗配置Excel檔案中進行更改，然後將檔案重新另存為制表符分隔的文本檔案。

如果已定義「開始」和「停止」時間，則沒有理由從實驗配置檔案中刪除實驗。 將所有實驗都列在實驗配置檔案中實際上是記錄如何定義每個實驗的好方法。

## 部署配置檔案和Test內容 {#section-34ff29649f584b93bc6129b75084b37c}

必須將實驗配置檔案部署到Web群集中運行 [!DNL Sensor] 並為實驗中涉及的頁面提供服務。 您可以使用手動過程或現有內容管理系統來執行此操作。

**部署test內容**

* 在運行 [!DNL Sensor] 即為實驗中涉及的頁面提供服務，請使用現有發佈過程將test內容部署到適當的位置。

   例如，如果要發佈test組頁 [!DNL index2.asp] 到網站的test資料夾( [!DNL mysite.com])，您會將檔案發佈到 [!DNL www.mysite.com/test]。

   >[!NOTE]
   >
   >不要從網站上的頁面直接連結到任何test檔案。 這樣做會使您的test結果和索引分數失效。

**部署實驗**

* 在運行 [!DNL Sensor] 為實驗中涉及的頁面提供服務的檔案，請將實驗配置文本檔案放在您在ExpFile參數中指定的目錄中 [!DNL Sensor] 配置檔案。 請參閱 [修改ExpFile參數](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

[!DNL Sensor] 根據您在檔案中定義的百分比隨機選擇每個組的網站訪問者，並根據需要為這些訪問者提供test或控制組內容。
