---
description: 客戶記錄服務(CRS)匯出功能可讓您將資料工作台資料匯出至Adobe Analytics核心服務，以與其他Analytics功能（包括報告與分析）整合。
title: 匯出至Analytics核心服務
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 匯出至Analytics核心服務{#exporting-to-analytics-core-services}

客戶記錄服務(CRS)匯出功能可讓您將資料工作台資料匯出至Adobe Analytics核心服務，以與其他Analytics功能（包括報告與分析）整合。

>[!NOTE]
>
>為了讓CRS匯出功能運作，訪客的Analytics ID必須以Experience Cloud ID服務(ECID)為基礎。 雖然訪客的資料工作台中可能會填入ECID，但如果客戶在寬限期內，或訪客的Cookie未被ECID取代，CRS匯出將不適用於該訪客。 如需詳細資訊，請參 [閱識別訪客](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html)[和ID服務寬限期](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html)。

從「詳 **細資料表** 」(在工作區中按一下滑鼠右鍵 **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** )，您可以設定屬性值和與Analytics的「報告與分析」整合所需的變數（使用Adobe Pipeline Services）。

1. **在表格標題上按一下滑鼠右鍵，然後按一下「新增客戶記錄服務」。**

   ![](assets/6_4_CRS.png)

1. **命名匯出檔案並儲存。**

   將會開啟導出檔案編輯窗口。

1. **開啟****查詢> CRS設定**。
1. **以滑鼠右鍵按一下「CRS屬性>新增」。**
1. **輸入** CRS ***屬性*****參數**。

   開啟新項目，並在匯出檔案的「 *CRS屬性* 」區段中輸入或驗證值：

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>屬性名稱</b> </p> </td> 
      <td colname="col2">顯示在「報告 <i>與分析」中</i> ，客戶屬 <i>性變數的名稱</i>。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>屬性類型</b> </td> 
      <td colname="col2"> <p>此參數接受(<i>int</i>, <i>string</i>)的值。 </p> <p>注意：如果屬性未 <b>在</b> Analytics中訂閱： <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">此屬性將使用Analytics支援的任何有效屬性類型建立(在此版本中，此屬性僅限 <i>於字串</i><i>和int</i>)。 </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">如果輸入無效的屬性類型，您會收到錯誤訊息，指出訂閱Analytics失敗。 </li> 
      </ul> </p> <p>如果屬性已 <b>在</b> Analytics中訂閱： </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">請務必為已訂閱的屬性輸入正確的屬性類型。 </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">如果您為屬性輸入了錯誤的類型，則其行為將取決於Analytics對屬性類型的處理。 </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>欄位名稱</b> </p> </td> 
      <td colname="col2">從中選擇屬性值的維或度量的名稱。 <p>注意：「 <i><b>CRS屬性</b></i> 」下方的「欄位名稱」應與「 <i>Output Fields</i> &gt; Field Name」 <b><i></i><i></i></b> （根據選取的屬性自動填入）相同。 如果欄 <i>位名稱</i> 無效，則匯出將不會執行。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 以滑鼠右鍵按 **[!UICONTROL Report Suite]** 一下> **[!UICONTROL Add New]**。
1. 輸入 **[!UICONTROL Report Suite ID]**.

   開啟新項目，並在匯出檔案的「報表套 *裝」區段中* ，輸入或驗證值：

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>報表套裝</b> </td> 
      <td colname="col2">「報告與分析」中識別 <i>要匯出之「客戶屬性</i> 」變 <i></i> 數的報表套裝ID。 <p> <p>注意：雖然「 <i>報告與分析</i> 」可讓您新增至多個報表套裝，但資料工作台6.4隻會匯出索引0所識別的單一報 <i>表套裝</i>。 <p>在此欄位中輸入的報表套裝值是報表套裝ID（而非報表套裝的名稱）。 </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 輸入ECID欄位參數。

   **ECID欄位**:描述檔中代表Adobe Experience Cloud ID的維度名稱。 這是必填欄位，所輸入的任何無效維度值都不會匯出。

1. （選用）填妥「訪客ID欄位」參數。

   **訪客ID欄位**:如果使用者想要傳送其資料中訪客的任何其他自訂ID，則會在此輸入代表自訂訪客ID的維度名稱。 這是可選欄位，可保留為空白。
