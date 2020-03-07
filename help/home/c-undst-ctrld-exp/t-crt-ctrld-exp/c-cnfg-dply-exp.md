---
description: 定義目標、假設和實驗詳細資訊並建立測試內容後，必須將感測器配置為部署受控實驗。
solution: Insight,Analytics
title: 設定和部署實驗
topic: Data workbench
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定和部署實驗{#configuring-and-deploying-the-experiment}

定義目標、假設和實驗詳細資訊並建立測試內容後，必須將感測器配置為部署受控實驗。

## 配置實驗配置檔案 {#section-037fe7dea9c94aee9cdc354dafdb7c03}

若要設定實驗，您必須完成Adobe提供的實驗設定試算表(依預設 [!DNL TestExperiment.xls] 命名)。 此檔案配 [!DNL Sensor] 置為執行實驗，是在修改ExpFile參數中指定的文本文 [件的Excel版本](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

此檔案可包含多個實驗的相關資訊，這些實驗可在相同或不同時間執行，並使用不同的群組和百分比，但這些實驗並無任何關聯。

使用者會被放入群組中，以供目前設定為執行的檔案中所列的每個實驗使用。

>[!NOTE]
>
>每個實驗都與所有其他實驗無關。 您對某個實驗所做的變更不會影響任何其他實驗，雖然訪客可能在多個實驗中，但結果不會彼此相關。 如果您認為多個實驗中的變更之間存在關聯，則必須建立新實驗來共同測試這些變更。

**若要設定您的實驗**

應在實驗開始之前完成此檔案，而不要在實驗運行時修改資訊。

>[!NOTE]
>
>如果實驗開始後實驗的定義發生變化，任何實驗都會立即失效。

1. 如果您擁有Web或應用程式伺服器的管理員存取權，請導覽至Web叢集中任 [!DNL Sensor] 何 [!DNL Sensor] 機器上的安裝資料夾以存取 [!DNL TestExperiment.xls] 檔案。 如果您沒有管理員存取權，請連絡您的Adobe客戶經理以請求 [!DNL TestExperiment.xls] 檔案。

1. 開啟檔 [!DNL TestExperiment.xls] 案（您可視需要重新命名此檔案）並填寫下列欄位：

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
   <td colname="col2"> <p>實驗的描述性名稱。 每個實驗名稱必須是唯一的，且不能包含空格。 </p> <p>在 <span class="keyword"> Insight中顯示實驗結果時，會使用實驗名稱 </span>。 這些名稱將作為受控實驗尺寸中的元素名稱的前半部分出現。 元素名稱的後半部分是此檔案中「群組」欄位的群組名稱。 每個群組都會使用實驗名稱后接群組名稱，以下列格式命名： </p> <p><i>EnperityName.Group名稱</i> </p> <p>例如： <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 開始 </td> 
   <td colname="col2"> <p>您希望實驗開始的日期和時間。 如果您未輸入值，則實驗會在檔案部署後立即開始。 </p> <p>格式：MM/DD/YYYY H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">如果您將開始和停止時間保留為空，則會無限期地執行實驗。 </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">您可以事先預先定義開始和停止時間；因此，您可以視需要一次設定下一年的所有實驗。 </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">啟動和停止時間取決於Web伺服器的系統時間。 如果該時鐘因任何原因而改變，您的實驗可能會意外地開始或停止。 </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">如果您想將實驗新增為設定檔案項目，但不希望實驗在不久的將來執行，則可使用數字元號"#"來注釋實驗資訊，或定義過去的開始和停止時間。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop </td> 
   <td colname="col2"> <p>您希望實驗結束的日期和時間。 當停止日期和時間發生時， <span class="wintitle"> Sensor </span> will stop send the cookie values idated as test group to test URIs and will send all cookies to the control group URIs. </p> <p>格式：MM/DD/YYYY H:MM </p> <p>請參閱「開始」欄位 <span class="wintitle"> 的 </span> 附註。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 群組 </td> 
   <td colname="col2"> <p>實驗中每組訪客的描述性名稱。 組名不能包含空格。 </p> <p>在Insight中顯示實驗結果時，會使用群組 <span class="keyword"> 名稱 </span>。 如需詳細資訊，請參閱「實驗」欄位說明。 </p> <p>控制組可以根據在「百分比」(Percentage)欄位中輸入的值隱式或顯式定義。 </p> <p> <p>注意： 若要符合實驗在定義時段內所需的訪客數量，以便在統計上有效，您可能需要降低信賴等級或增加時段。 例如，若您的時間範圍是5天，您的信賴等級為98%，而您所需的訪客數量超過該時段的預期數量，則您需要增加時段或降低信賴等級，直到預期的訪客數量超過執行統計有效實驗所需的數量為止。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 百分比 </td> 
   <td colname="col2"> <p>每個定義群組中要包含的網站訪客百分比。 這些值可以表示為百分比或小數值。 此外，兩個值必須大於或等於一。 </p> <p>例如： </p> <p>33.3%和66.7% </p> <p>.99和。01 </p> <p>如果所有群組的總和小於100，未定義的超額預設為控制群組。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 原始URL </td> 
   <td colname="col2"> <p>要重新映射的內容的URI，後面是$。 此值區分大小寫。 </p> <p>格式：index.asp$ </p> <p>可以在URI結尾處使用美元符號($)指定原始URI，以表示需要完全符合檔案名稱。 例如，運算式 <span class="filepath"> /product/product_view.asp$ </span> 僅與該頁面相符，而 <span class="filepath"></span><span class="filepath"></span> /product則與/product目錄中的任何頁面相符，可用來重新映射整個子樹。 實驗會忽略未在檔案名稱結尾指定$字元的原始URL項目，除非ExpPartialMatch參數已設為"on"。有關此參數的詳細資訊，請參 <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> 閱修改ExpPartialMatch參數（可選） </a>。 </p> <p>受控實驗功能忽略附加到URI乾的任何查詢字串。 例如，頁面 </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982 </span> 不是有效的URI，但頁 <span class="filepath"> 面/product/product_view.asp </span> 是有效的URI。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重新映射的URL </td> 
   <td colname="col2"> <p>替代內容的URI。 </p> <p>格式：index2.asp </p> <p>請參閱「原始URL」欄位的附註。 </p> </td> 
  </tr> 
 </tbody> 
</table>

以下是已完成試算表的范 [!DNL TextExperiment.xls] 例：

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>請勿修改試算表中的欄位。

此範例指出「New_Homepage」實驗從2006年6月1日開始，於2006年6月30日結束，其中包含包含50%訪客的控制群組和包含50%訪客的測試群組，這些訪客會針對一個URI看到不同的內容。

>[!NOTE]
>
>儘管上述示例檔案已定義了明確的控制組，但不需要顯式定義控制組— 實驗會自動建立控制群組。 如果實驗中所有群組的百分比總和小於100%，則會將隱含控制群組指派給不屬於其中一個明確群組的使用者。

1. 若要插入注釋以提供有關特定實驗的其他資訊，請在儲存格開頭加上數字元號(#)，然後依照您的注釋進行。 注釋可以插入檔案的任意位置。
1. 在實驗配置試算表中完成變數後，請儲存變更，然後使用您在設定檔中的ExpFile參數中指定的名稱，以Tab分隔文字格式( [!DNL *.txt])儲存 [!DNL Sensor] 檔案。 請參 [閱修改ExpFile參數](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

   以下是實驗配置文本檔案的示例：

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >由於此檔案中需要有頁籤，因此不要手動編輯實驗配置文本檔案。 如果您需要變更檔案，請在實驗設定Excel檔案中進行變更，然後將檔案重新儲存為以Tab分隔的文字檔案。

如果您已定義「開始」和「停止」時間，則沒有理由從實驗配置檔案中刪除實驗。 將實驗設定檔中列出的所有實驗都保留下來，其實是記錄每個實驗的定義方式的好方法。

## 部署配置檔案並測試內容 {#section-34ff29649f584b93bc6129b75084b37c}

您必須將實驗配置檔案部署到運行並為實驗所涉及頁提供服務的 [!DNL Sensor] Web群集中的每台電腦。 您可以使用手動過程或現有的內容管理系統來完成此操作。

**若要部署您的測試內容**

* 在執行提供實驗相關頁面的應 [!DNL Sensor] 用程式或網頁伺服器上，使用您現有的發佈程式將測試內容部署至適當的位置。

   例如，如果您想要將測試群組頁面發佈 [!DNL index2.asp] 至網站( [!DNL mysite.com])的測試資料夾，您會將檔案發佈至 [!DNL www.mysite.com/test]。

   >[!NOTE]
   >
   >請勿直接從您網站上的頁面連結至任何測試檔案。 這樣做會使測試結果和索引分數無效。

**若要部署您的實驗**

* 在運行服務實驗中涉及頁的 [!DNL Sensor] 每個應用程式或Web伺服器上，將實驗配置文本檔案放置在配置檔案中ExpFile參數中指定的 [!DNL Sensor] 目錄中。 請參 [閱修改ExpFile參數](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

[!DNL Sensor] 根據您在檔案中定義的百分比隨機選取每個群組的網站訪客，並視需要為其提供測試或控制群組內容。
