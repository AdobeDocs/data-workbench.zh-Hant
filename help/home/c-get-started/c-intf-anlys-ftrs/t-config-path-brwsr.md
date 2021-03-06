---
description: 路徑瀏覽器可設定為搭配任何對您的應用程式和資料集有意義的基本維度、群組維度、層級維度和量度組合使用。
title: 設定路徑瀏覽器
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
exl-id: be6a68f7-e3e3-4207-a112-3a4fdd5c5f57
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 2%

---

# 設定路徑瀏覽器{#configure-a-path-browser}

路徑瀏覽器可設定為搭配任何對您的應用程式和資料集有意義的基本維度、群組維度、層級維度和量度組合使用。

配置路徑瀏覽器後，該路徑瀏覽器會與[!DNL Add Visualization]菜單中的其他路徑瀏覽器一起列出。

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Menu]**，然後按一下&#x200B;**[!UICONTROL Add Visualization]**&#x200B;和&#x200B;**[!UICONTROL Path Browser]**。

   路徑瀏覽器目錄中至少有一個[!DNL *.vw]檔案。

1. 按一下右鍵所需檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。
1. 按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。
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
   <td colname="col2"> <p>基礎維的級別（父級）名稱，您將其元素拖動到路徑瀏覽器。 當您沿著一個基本維度元素到下一個的路徑時，會從一個層級維度元素移至下一個。 選擇基本維元素的路徑時，將為級別維的相應元素選擇資料。 選取始終包括與根相關的級別維的元素，並且通過向路徑添加更多元素來細化它。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>量度名稱</i> </p> </td> 
   <td colname="col2"> <p>量度的名稱，其指定元素的值與通向該元素的路徑的厚度成比例。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>如需路徑瀏覽器的基本維度、群組維度、層級維度和量度的詳細資訊，請參閱[路徑瀏覽器](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b)。

1. 在記事本中，按一下&#x200B;**[!UICONTROL File]** > **[!UICONTROL Save As]**&#x200B;以基於組維的新名稱保存檔案，即&#x200B;*組維名*.vw。

   請務必將檔案儲存至「路徑瀏覽器」目錄。

   >[!NOTE]
   >
   >要確保路徑瀏覽器保存為[!DNL *.vw]檔案，請在[!DNL Save As]窗口中，將「另存為」類型設定為「所有檔案」。

1. （可選）要使工作配置檔案的所有用戶都能使用更改，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中的檔案複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***。
