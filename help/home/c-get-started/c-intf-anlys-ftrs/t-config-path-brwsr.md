---
description: 路徑瀏覽器可設定為搭配任何基本維度、群組維度、層級維度和量度的組合使用，這對您的應用程式和資料集而言都有意義。
solution: Analytics
title: 設定路徑瀏覽器
topic: Data workbench
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定路徑瀏覽器{#configure-a-path-browser}

路徑瀏覽器可設定為搭配任何基本維度、群組維度、層級維度和量度的組合使用，這對您的應用程式和資料集而言都有意義。

在您設定路徑瀏覽器後，會在選單中與其他路徑瀏覽器一起 [!DNL Add Visualization] 列出。

1. 在中， [!DNL Profile Manager]按一下 **[!UICONTROL Menu]**，然後按一下 **[!UICONTROL Add Visualization]** 並 **[!UICONTROL Path Browser]**。

   至少有一 [!DNL *.vw] 個檔案駐留在路徑瀏覽器目錄中。

1. 按一下右鍵所需檔案的複選標籤，然後按一下 **[!UICONTROL Make Local]**。
1. 按一下右鍵列中檔案的複選標籤， [!DNL User] 然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。
1. 使用下列範例檔案和表格作為參考線編輯檔案的參數：

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
   <td colname="col1"> <p><i>基本維名</i> </p> </td> 
   <td colname="col2"> <p>其元素出現在路徑瀏覽器中的維的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>群組維度名稱</i> </p> </td> 
   <td colname="col2"> <p>決定層級維元素如何分組以在路徑瀏覽器中形成路徑的維的名稱。 具體而言，與路徑瀏覽器中單一路徑相關聯的層級維度元素不能跨越群組維度的多個元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>級別維名稱</i> </p> </td> 
   <td colname="col2"> <p>將元素拖曳至路徑瀏覽器的基本維的級別（父級）名稱。 當您沿著一個基本維度元素到下一個維度元素的路徑時，您會從一個層級維度元素移至下一個層級。 選擇基本維元素的路徑時，將為級別維的相應元素選擇資料。 選取範圍始終包含與根相關的級別維的元素，並通過向路徑添加更多元素來細化它。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>量度名稱</i> </p> </td> 
   <td colname="col2"> <p>指定元素的值與該元素所在路徑的厚度成比例的度量名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>如需路徑瀏覽器的基本維度、群組維度、層級維度和量度的詳細資訊，請參閱路徑瀏 [覽器](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b)。

1. 在記事本中，按 **[!UICONTROL File]** > **[!UICONTROL Save As]** 以根據群組維度(即群組維度名稱 **.vw)，以新名稱儲存檔案。

   請務必將檔案儲存至「路徑瀏覽器」目錄。

   >[!NOTE]
   >
   >要確保路徑瀏覽器保存為檔案，請在窗口 [!DNL *.vw] 中將「另存為類型」 [!DNL Save As] 設定為「所有檔案」。

1. （可選）要使更改可供工作配置檔案的所有用戶使用，請在列中按一下右鍵該檔案的複選標籤，然後按一下 [!DNL Profile Manager]> [!DNL User] &lt; **[!UICONTROL Save to]** > ***[!UICONTROL working profile name]***。