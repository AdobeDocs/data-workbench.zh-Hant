---
description: 客戶記錄服務(CRS)匯出功能可讓您將Data Workbench資料匯出至Adobe Analytics核心服務，以與其他Analytics功能整合，包括Reports & Analytics。
title: 匯出至 Analytics 核心服務
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
exl-id: 573085e8-2260-4872-be90-a84ad61145bb
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 2%

---

# 匯出至 Analytics 核心服務{#exporting-to-analytics-core-services}

客戶記錄服務(CRS)匯出功能可讓您將Data Workbench資料匯出至Adobe Analytics核心服務，以與其他Analytics功能整合，包括Reports &amp; Analytics。

>[!NOTE]
>
>為了讓CRS匯出功能正常運作，訪客的Analytics ID必須以Experience CloudID服務(ECID)為基礎。 雖然ECID可以填入至訪客的Data Workbench中，但如果用戶端位於寬限期，或訪客的Cookie未取代為ECID，則CRS匯出將無法用於該訪客。 如需詳細資訊，請參閱[識別訪客](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html)和[ID服務寬限期](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html)。

在&#x200B;**詳細資料表格**（在工作區中按一下滑鼠右鍵&#x200B;**[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**），您可以設定屬性值和必要變數，以便與Analytics的Reports &amp; Analytics整合(使用Adobe管道服務)。

1. **以滑鼠右鍵按一下表格標題，然後按一下「新增客戶記錄服務」。**

   ![](assets/6_4_CRS.png)

1. **為匯出檔案命名並儲存。**

   將開啟導出檔案編輯窗口。

1. **** **OpenQuery > CRS設定**。
1. **以滑鼠右鍵按一下「CRS屬性>新增」。**
1. **** ***輸入CRS*** **屬性參數**。

   開啟新項目，然後在匯出檔案的&#x200B;*CRS屬性*&#x200B;區段中輸入或驗證值：

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>屬性名稱</b> </p> </td> 
      <td colname="col2">顯示在<i>Reports &amp; Analytics</i>中的<i>客戶屬性</i>變數名稱。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>屬性類型</b> </td> 
      <td colname="col2"> <p>此參數接受(<i>int</i>, <i>string</i>)的值。 </p> <p>注意：如果屬性是<b>未</b>訂閱Analytics中的： <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">屬性將會以Analytics支援的任何有效屬性類型建立（在此版本中，僅限<i>string</i>和<i>int</i>）。 </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">如果輸入無效的屬性類型，您會收到錯誤訊息，指出無法訂閱Analytics。 </li> 
      </ul> </p> <p>如果屬性已訂閱<b>,</b>，則在Analytics中： </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">請務必為已訂閱屬性的輸入正確的屬性類型。 </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">如果您為屬性輸入錯誤的類型，則其行為將取決於Analytics處理屬性類型的方式。 </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>欄位名稱</b> </p> </td> 
      <td colname="col2">從中選取屬性值的維度或量度名稱。 <p>注意：<i><b><i>CRS屬性</i>下的欄位名稱</b></i>應與<b><i>輸出欄位</i> &gt; <i>欄位名稱</i></b>相同（會根據所選屬性自動填入）。 如果<i>欄位名稱</i>無效，則導出將不運行。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 按一下右鍵&#x200B;**[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**。
1. 輸入 **[!UICONTROL Report Suite ID]**.

   開啟新項目，然後在匯出檔案的&#x200B;*報表套裝*&#x200B;區段中輸入或驗證值：

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>報表套裝</b> </td> 
      <td colname="col2"><i>Reports &amp; Analytics</i>中識別要匯出的<i>客戶屬性</i>變數的報表套裝ID。 <p> <p>注意：雖然<i>Reports &amp; Analytics</i>可讓您新增至多個報表套裝，但Data Workbench6.4隻會匯出以<i>索引0</i>識別的單一報表套裝。 <p>在此欄位中輸入的報表套裝值是報表套裝ID（而非報表套裝的名稱）。 </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 輸入ECID欄位參數。

   **ECID欄位**:描述檔中代表Adobe Experience Cloud ID的維度名稱。這是必填欄位，所輸入的任何無效維度值都不會匯出。

1. （選用）填入訪客ID欄位參數。

   **訪客ID欄位**:如果使用者想在其資料中傳送任何其他訪客的自訂ID，即為使用者輸入維度名稱（代表自訂訪客ID）的位置。此為選用欄位，可保留空白。
