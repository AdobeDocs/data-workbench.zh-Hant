---
description: 您可以在流程映射中進行選擇，以建立包含或排除與特定節點關聯的資料的篩選器。
title: 從程序圖中進行選取
uuid: 7fd00090-c9ab-4bb6-8584-7de7b6f4b68c
exl-id: 8ede395f-906a-49e0-8ff8-b43a326275e5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# 從程序圖中進行選取{#make-a-selection-from-a-process-map}

您可以在流程映射中進行選擇，以建立包含或排除與特定節點關聯的資料的篩選器。

在流程圖中進行選擇涉及映射的組維，該組維確定如何對基本維的元素（即映射中的節點）進行分組以在節點之間形成連接。

>[!NOTE]
>
>您可以更改流程映射的預設組維。 請參閱[配置進程映射](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6)。

當根據進程映射中的節點進行選擇時，將選擇與該節點相關的組維的所有元素。 要更好地瞭解組維的角色，請考慮以下示例：

* 影片可依對影片評分的觀眾分組。 每個檢視器都是「使用者」維度的元素，因此「使用者」維度會是流程圖的群組維度。 當您從特定影片的節點進行選擇時，會建立篩選器，顯示已播放或未播放該影片的使用者的資料。
* 網站頁面可依其檢視的作業階段分組。 每個會話都是「會話」維的元素，因此「會話」維將是進程映射的組維。 從特定頁面的節點進行選擇時，您會建立篩選器，顯示該頁面被檢視或未被檢視之作業的資料。

**要進行選擇**

1. 按一下右鍵進程映射中的任何節點。
1. 按一下以下選項之一以根據節點進行選擇：

   * **[!UICONTROL Select]***  **[!UICONTROL group dimension name +s]***  **[!UICONTROL through node name]**:篩選資料，將未通過節點的所有會話篩選掉，以包含通過節點的組維的所有元素。

   * **[!UICONTROL Select]***  **[!UICONTROL group dimension name +s]***  **[!UICONTROL NOT through node name]**:篩選資料，將未通過節點的群組維度的所有元素納入其中，方法是篩選掉通過節點的所有會話。

![](assets/vis_2DProcessMap_Selections_Movie.png)

![](assets/vis_2DProcessMap_Selections_Page.png)

在3D工藝圖中進行選取時，將圍繞進行選取的節點。 基準會出現在每個列的周圍，協助您比較有無選擇的量度值。 請參閱[瞭解基準](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914)。

![](assets/vis_3DProcessMap_Selection.png)
