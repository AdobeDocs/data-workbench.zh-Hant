---
description: 路徑瀏覽器可設定為搭配任何對您的應用程式和資料集有意義的基本維度、群組維度、層級維度和量度組合使用。
title: 設定路徑瀏覽器
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
exl-id: be6a68f7-e3e3-4207-a112-3a4fdd5c5f57
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 1%

---

# 設定路徑瀏覽器{#configure-a-path-browser}

{{eol}}

路徑瀏覽器可設定為搭配任何對您的應用程式和資料集有意義的基本維度、群組維度、層級維度和量度組合使用。

配置路徑瀏覽器後，該瀏覽器會與 [!DNL Add Visualization] 功能表。

1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Menu]**，然後按一下 **[!UICONTROL Add Visualization]** 和 **[!UICONTROL Path Browser]**.

   至少一個 [!DNL *.vw] 檔案位於路徑瀏覽器目錄中。

1. 以滑鼠右鍵按一下所需檔案的核取記號，然後按一下 **[!UICONTROL Make Local]**.
1. 以滑鼠右鍵按一下 [!DNL User] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. 使用以下示例檔案和表作為參考線編輯檔案的參數：

   ```
   window = simpleBorderWindow: 
     client = pathBrowser: 
       Left Path = vector: 0 items
       Map = ref: wdata/model/dim/base dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       Map Level = ref: wdata/model/dim/level dimension name
       Metric = ref: wdata/model/metric/metric name
       Right Path = vector: 0 items
       size = v3d: (673, 279, 0)
     pos = v3d: (714, 143, 0)
     size = v3d: (673, 298, 0)
   ```

<table id="table_1DCCB4B24B554B72A781B304B5EB155E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對於此參數…… </th> 
   <th colname="col2" class="entry"> 提供此資訊…… </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>基本維名稱</i> </p> </td> 
   <td colname="col2"> <p>元素出現在路徑瀏覽器上的維的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>組維名稱</i> </p> </td> 
   <td colname="col2"> <p>決定如何對層級維度的元素進行分組，以在路徑瀏覽器中形成路徑的維度名稱。 具體而言，與路徑瀏覽器中的單一路徑相關聯的層級維度元素不能跨越多個群組維度的元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>級別維名稱</i> </p> </td> 
   <td colname="col2"> <p>基礎維的級別（父級）名稱，您將其元素拖動到路徑瀏覽器。 當您沿著一個基本維度元素到下一個的路徑時，會從一個層級維度元素移至下一個層級。 選擇基本維元素的路徑時，將為級別維的相應元素選擇資料。 選取始終包括與根相關的級別維的元素，並且通過向路徑添加更多元素來細化它。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>量度名稱</i> </p> </td> 
   <td colname="col2"> <p>量度的名稱，其指定元素的值與通向該元素的路徑的厚度成比例。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>如需路徑瀏覽器的基本維度、群組維度、層級維度和量度的詳細資訊，請參閱 [路徑瀏覽器](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. 在記事本中，按一下 **[!UICONTROL File]** > **[!UICONTROL Save As]** 要根據組維以新名稱保存檔案，即， *組維名稱*.vw.

   請務必將檔案儲存至「路徑瀏覽器」目錄。

   >[!NOTE]
   >
   >確保路徑瀏覽器儲存為 [!DNL *.vw] 檔案中 [!DNL Save As] 窗口，將「另存為類型」設定為「所有檔案」。

1. （選用）若要讓變更可供工作設定檔的所有使用者使用，請在 [!DNL Profile Manager]，請在 [!DNL User] 欄，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
