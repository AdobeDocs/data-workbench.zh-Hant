---
description: 定義目標、假設和實驗詳細資訊並建立測試內容後，必須配置Sensor以部署受控實驗。
solution: Analytics
title: 設定和部署實驗
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
exl-id: 957c2ea2-72a5-4bb2-af1d-65187613c26d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# 設定和部署實驗{#configuring-and-deploying-the-experiment}

{{eol}}

定義目標、假設和實驗詳細資訊並建立測試內容後，必須配置Sensor以部署受控實驗。

## 配置實驗配置檔案 {#section-037fe7dea9c94aee9cdc354dafdb7c03}

若要設定實驗，您必須完成Adobe提供的實驗設定試算表(名為 [!DNL TestExperiment.xls] )。 此檔案會設定 [!DNL Sensor] 來執行實驗，且是您在 [修改ExpFile參數](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

此檔案可包含多個實驗的相關資訊，這些實驗可在相同或不同時間執行，且使用不同的群組和百分比，但這些實驗絕不相關聯。

針對檔案中所列的每個實驗，將使用者放入群組，該檔案設定目前執行。

>[!NOTE]
>
>每個實驗都與所有其他實驗無關。 您對一個實驗所做的變更不會影響任何其他實驗，雖然訪客可能在多個實驗中，但結果並不相關。 如果您認為多個實驗中的變更之間存在關聯，則必須建立一個新實驗來同時測試這些變更。

**設定實驗的方式**

您應在實驗開始前完成此檔案，而不是在實驗執行期間修改資訊。

>[!NOTE]
>
>如果實驗開始後實驗的定義發生變化，則任何實驗都會立即失效。

1. 如果您有Web或應用程式伺服器的管理員存取權，請導覽至 [!DNL Sensor] 任何 [!DNL Sensor] Web群集中的電腦以訪問 [!DNL TestExperiment.xls] 檔案。 如果您沒有管理員存取權，請連絡您的Adobe帳戶管理員以要求 [!DNL TestExperiment.xls] 檔案。

1. 開啟 [!DNL TestExperiment.xls] 檔案（您可以視需要重新命名此檔案）並填入下列欄位：

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
   <td colname="col2"> <p>實驗的描述性名稱。 每個實驗名稱必須是唯一的，且不能包含空格。 </p> <p>在中顯示實驗結果時，會使用實驗名稱 <span class="keyword"> 分析 </span>. 這些名稱會顯示為受控實驗維度中元素名稱的前半部。 元素名稱的後半部分是此檔案中「群組」欄位中的群組名稱。 每個群組的命名格式如下，使用實驗名稱，後接群組名稱： </p> <p><i>ExperienceName.Group名稱</i> </p> <p>例如： <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 開始 </td> 
   <td colname="col2"> <p>您希望實驗開始的日期和時間。 如果您未輸入值，則實驗會在檔案部署後立即開始。 </p> <p>格式：MM/DD/YYYY H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">如果您將開始和停止時間保留為空白，則實驗會無限期執行。 </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">您可以提前預定開始和停止時間；因此，您可以視需要一次為下一年設定所有實驗。 </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">啟動和停止時間取決於Web伺服器的系統時間。 如果該時鐘因任何原因而改變，您的實驗可能會意外地開始或停止。 </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">如果您想要將實驗新增為設定檔案項目，但不希望該實驗在不久的將來執行，則可以使用數字型大小「#」來註解實驗資訊，或定義過去的開始和停止時間。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop </td> 
   <td colname="col2"> <p>您希望實驗結束的日期和時間。 停止日期和時間發生時， <span class="wintitle"> 感測器 </span> 將停止將標識為測試組的cookie值發送到測試URI，並將所有cookie發送到控制組URI。 </p> <p>格式：MM/DD/YYYY H:MM </p> <p>請參閱 <span class="wintitle"> 開始 </span> 欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 群組 </td> 
   <td colname="col2"> <p>實驗中每組訪客的描述性名稱。 組名不能包含空格。 </p> <p>群組名稱會用於顯示 <span class="keyword"> 分析 </span>. 如需詳細資訊，請參閱實驗欄位說明。 </p> <p>可以根據在「百分比」欄位中輸入的值隱式或顯式定義控制組。 </p> <p> <p>注意：若要符合在定義時段內要讓實驗具有統計效力所需的訪客數量，您可能需要降低信賴等級或增加時段。 例如，如果您的時間範圍為5天，您的信賴水準為98%，而您需要的訪客數量超過該時段的預期數量，則您需要增加時段或降低信賴水準，直到預期的訪客數量超過執行統計有效實驗所需的數量為止。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 百分比 </td> 
   <td colname="col2"> <p>每個已定義群組中包含的網站訪客百分比。 這些值可以以百分比或小數值表示。 此外，兩個值必須大於或小於一。 </p> <p>例如： </p> <p>33.3%和66.7% </p> <p>.99和。01 </p> <p>如果所有組的總和小於100，則未定義的超出預設為控制組。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 原始URL </td> 
   <td colname="col2"> <p>要重新映射的內容的URI，後面跟$。 此值區分大小寫。 </p> <p>格式：index.asp$ </p> <p>可以使用URI末尾的美元符號($)指定原始URI，以表示需要與檔案名完全匹配。 例如，運算式 <span class="filepath"> /product/product_view.asp$ </span> 僅符合該確切頁面，而 <span class="filepath"> /product </span> 比對中的任何頁面 <span class="filepath"> /product </span> 目錄，可用來重新映射整個子樹。 實驗會忽略未在檔案名稱結尾指定$字元的原始URL項目，除非ExpPartialMatch參數已設為「on」。 如需此參數的詳細資訊，請參閱 <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> 修改ExpPartialMatch參數（選用） </a>. </p> <p>受控實驗功能會忽略附加到URI主體的任何查詢字串。 例如，頁面 </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982 </span> 不是有效的URI，但是頁面 <span class="filepath"> /product/product_view.asp </span> 是有效的URI。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重新映射的URL </td> 
   <td colname="col2"> <p>替代內容的URI。 </p> <p>格式：index2.asp </p> <p>請參閱原始URL欄位的附註。 </p> </td> 
  </tr> 
 </tbody> 
</table>

以下是已完成的範例 [!DNL TextExperiment.xls] 試算表：

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>請勿修改試算表中的欄位。

此範例指出，「New_Homepage」實驗從2006年6月1日開始，於2006年6月30日結束，其中包含包含50%訪客的控制群組，以及包含50%訪客的測試群組，這些訪客在一個URI中看到不同內容。

>[!NOTE]
>
>儘管上述示例檔案定義了顯式控制組，但不需要顯式定義控制組 — 實驗會自動建立控制組。 如果實驗中所有群組的百分比總和小於100%，則會將隱含控制組指派給未落入其中一個明確群組的使用者。

1. 若要插入註解以提供特定實驗的其他資訊，請以數字型大小(#)開頭儲存格，然後遵循您的註解。 注釋可以插入檔案中的任意位置。
1. 在實驗設定試算表中完成變數後，請儲存變更，然後以定位點分隔的文字格式( [!DNL *.txt])，使用您在 [!DNL Sensor] 設定檔。 請參閱 [修改ExpFile參數](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   以下是實驗組態文字檔的範例：

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >由於此檔案中需要頁簽，因此請勿手動編輯實驗配置文本檔案。 如果您需要變更檔案，請在實驗設定Excel檔案中進行變更，並將檔案重新儲存為以定位點分隔的文字檔案。

如果您已定義「開始」和「停止」時間，則沒有理由從實驗設定檔案中刪除實驗。 將所有實驗列在實驗設定檔案中實際上是記錄每個實驗的定義方式的好方法。

## 部署設定檔案並測試內容 {#section-34ff29649f584b93bc6129b75084b37c}

必須將實驗配置檔案部署到運行 [!DNL Sensor] 並提供實驗中涉及的頁面。 您可以使用手動過程或您現有的內容管理系統執行此操作。

**部署測試內容**

* 在運行 [!DNL Sensor] 提供實驗中涉及的頁面，請使用現有的發佈程式將測試內容部署至適當的位置。

   例如，如果您要發佈測試群組頁面 [!DNL index2.asp] 至網站的測試資料夾( [!DNL mysite.com])，您就會將檔案發佈到 [!DNL www.mysite.com/test].

   >[!NOTE]
   >
   >請勿從網站上的頁面直接連結至任何測試檔案。 這樣做會使測試結果和索引分數失效。

**部署實驗**

* 在運行 [!DNL Sensor] 提供實驗相關頁面的，請將實驗配置文本檔案置於ExpFile參數中指定的目錄(位於 [!DNL Sensor] 設定檔。 請參閱 [修改ExpFile參數](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

[!DNL Sensor] 根據您在檔案中定義的百分比，隨機選取每個群組的網站訪客，並視需要提供測試或控制群組內容給他們。
