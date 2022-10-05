---
description: 程式圖可經過設定，以搭配任何對您的應用程式和資料集有意義的基本維度、群組維度、層級維度和量度組合使用。
title: 設定程序圖
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
exl-id: 0b37e942-4596-45cc-bc31-db147626f4eb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 1%

---

# 設定程序圖{#configure-a-process-map}

{{eol}}

程式圖可經過設定，以搭配任何對您的應用程式和資料集有意義的基本維度、群組維度、層級維度和量度組合使用。

配置進程圖後，該進程圖將與 [!DNL Add Visualization menu].

1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Menu]**，按一下 **[!UICONTROL Add Visualization]**，然後按一下要配置的進程映射類型（2D度量映射、2D進程映射或3D進程映射）。

   至少一個 [!DNL *.vw] 檔案位於目錄中。

1. 以滑鼠右鍵按一下所需檔案的核取記號，然後按一下 **[!UICONTROL Make Local]**.
1. 以滑鼠右鍵按一下 [!DNL User] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. 使用以下示例檔案和表作為參考線編輯檔案的參數：

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
   <td colname="col1"> <p><i>基本維名稱</i> </p> </td> 
   <td colname="col2"> <p>其元素在進程圖中顯示為節點的維的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>級別維名稱</i> </p> </td> 
   <td colname="col2"> <p>基礎維的級別（父級）名稱，您將其元素拖動到流程圖。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>組維名稱</i> </p> </td> 
   <td colname="col2"> <p>決定如何對級別維的元素進行分組以在節點之間建立連接的維的名稱。 兩個節點之間的連接不能跨越組維的多個元素。 當您根據進程映射中的節點進行選擇時，將選擇與該節點相關的組維的所有元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>量度映射的量度名稱</i> </p> </td> 
   <td colname="col2"> <p>此參數僅適用於2D量度對應。 </p> <p>量度的名稱，其值會決定地圖上節點的水準位置。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>如需程式圖的基本維度、群組維度、層級維度和量度的詳細資訊，請參閱 [程式圖](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

1. 在記事本中，按一下 **[!UICONTROL File]** > **[!UICONTROL Save As]** 以基於基本維的新名稱保存檔案，即， *基本維名稱*.vw.

   (如果您要設定2D量度對應，應根據量度對應的量度名稱(即， *量度映射的量度名稱*.vw) 請務必將檔案儲存至適當的程式圖目錄。

   >[!NOTE]
   >
   >確認您的程式圖已儲存為 [!DNL *.vw] 檔案中 [!DNL Save As] 窗口，將「另存為類型」設定為「所有檔案」。

1. （選用）若要讓變更可供工作設定檔的所有使用者使用，請在 [!DNL Profile Manager]，請在 [!DNL User] 欄，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
