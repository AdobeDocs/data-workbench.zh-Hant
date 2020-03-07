---
description: 流程地圖可設定為搭配任何對您的應用程式和資料集有意義的基本維度、群組維度、層級維度和量度組合使用。
solution: Analytics
title: 配置進程映射
topic: Data workbench
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置進程映射{#configure-a-process-map}

流程地圖可設定為搭配任何對您的應用程式和資料集有意義的基本維度、群組維度、層級維度和量度組合使用。

配置進程映射後，它將與中的其他進程映射一起列出 [!DNL Add Visualization menu]。

1. 在中， [!DNL Profile Manager]按一下 **[!UICONTROL Menu]**，單 **[!UICONTROL Add Visualization]**&#x200B;擊，然後按一下要配置的流程映射類型（2D度量映射、2D流程映射或3D流程映射）。

   目錄中至 [!DNL *.vw] 少有一個檔案。

1. 按一下右鍵所需檔案的複選標籤，然後按一下 **[!UICONTROL Make Local]**。
1. 按一下右鍵列中檔案的複選標籤， [!DNL User] 然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。
1. 使用下列範例檔案和表格作為參考線編輯檔案的參數：

   ```
   window = simpleBorderWindow: 
     client = processMap: 
       Traffic Metric = ref: wdata/model/metric/metric name
       center = v3d: (-0.741014, 0, 0.0639476)
       color_links = bool: true
       Map = PrefixDim: 
         Name = string: Map
         Base Dimension = ref: wdata/model/dim/base dimension name
         Element Prefixes = vector: 0 items
         Element Names = vector: 0 items
       Map Level = ref: wdata/model/dim/level dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       node_label = vector<bool>: 
       node_positions = vector: 0 items
       quantify_links = int: 2
       range = double: 2.37386
       size = v3d: (430, 290, 0)
       xAxisMetric = ref: wdata/model/metric/metric name for metric map
     pos = v3d: (880, 595, 0)
     size = v3d: (430, 309, 0)
   ```

<table id="table_3F072DB1B68746C49DF9332718982EBE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對於此參數…… </th> 
   <th colname="col2" class="entry"> 提供此資訊…… </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>量度名稱</i> </p> </td> 
   <td colname="col2"> <p>指定節點的值與節點大小成比例的度量名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>基本維名</i> </p> </td> 
   <td colname="col2"> <p>其元素在進程映射中顯示為節點的維的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>級別維名稱</i> </p> </td> 
   <td colname="col2"> <p>基本維的級別（父級）的名稱，您將其元素拖動到流程映射。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>群組維度名稱</i> </p> </td> 
   <td colname="col2"> <p>確定級別維元素如何分組以在節點之間形成連接的維的名稱。 兩個節點之間的連接不能跨組維的多個元素。 當根據進程映射中的節點進行選擇時，將選擇與該節點相關的組維的所有元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>量度映射的量度名稱</i> </p> </td> 
   <td colname="col2"> <p>此參數僅適用於2D量度對應。 </p> <p>量度的名稱，其值會決定節點在地圖上的水準位置。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>有關流程映射的基本維、組維、級別維和度量的詳細資訊，請參閱流程 [映射](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e)。

1. 在記事本中，按 **[!UICONTROL File]** > **[!UICONTROL Save As]** 以根據基本維度(即基本維度名稱 **.vw)，以新名稱儲存檔案。

   (如果您要設定2D量度地圖，則應根據量度地圖的量度名稱(即量度map **.vw的量度名稱)，以名稱儲存檔案。)請確保將檔案保存到相應的進程映射目錄。

   >[!NOTE]
   >
   >要確保將流程映射保存為檔案，請在窗 [!DNL *.vw] 口中將「另存為類 [!DNL Save As] 型」設定為「所有檔案」。

1. （可選）要使更改可供工作配置檔案的所有用戶使用，請在列中按一下右鍵該檔案的複選標籤，然後按一下 [!DNL Profile Manager]> [!DNL User] &lt; **[!UICONTROL Save to]** > ***[!UICONTROL working profile name]***。
