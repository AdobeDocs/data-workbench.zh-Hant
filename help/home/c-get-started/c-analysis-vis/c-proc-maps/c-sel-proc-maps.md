---
description: 您可以在進程映射中進行選擇，以建立包含或排除與特定節點關聯的資料的篩選器。
title: 從程序圖中進行選取
uuid: 7fd00090-c9ab-4bb6-8584-7de7b6f4b68c
exl-id: 8ede395f-906a-49e0-8ff8-b43a326275e5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# 從程序圖中進行選取{#make-a-selection-from-a-process-map}

{{eol}}

您可以在進程映射中進行選擇，以建立包含或排除與特定節點關聯的資料的篩選器。

在進程映射中進行選擇涉及映射的組維，該維確定如何對基本維的元素（即映射中的節點）進行分組以形成節點之間的連接。

>[!NOTE]
>
>您可以更改流程圖的預設組維。 請參閱 [設定程式圖](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).

當您根據進程映射中的節點進行選擇時，將選擇與該節點相關的組維的所有元素。 若要更清楚了解群組維度的角色，請考量下列範例：

* 電影可依對影片進行分級的觀眾分組。 每個檢視器都是「使用者」維度的元素，因此「使用者」維度會是程式圖的群組維度。 當您從某個節點選擇特定電影時，會建立一個篩選器來顯示已對該電影進行評分或未對該電影進行評分的用戶的資料。
* 網站頁面可依其檢視的工作階段分組。 每個工作階段都是「工作階段」維度的元素，因此「工作階段」維度會是程式圖的群組維度。 從特定頁面的節點進行選取時，您會建立篩選器，顯示該頁面被檢視或未被檢視之工作階段的資料。

**進行選擇**

1. 按一下右鍵進程映射中的任何節點。
1. 按一下以下任一選項，以根據節點進行選取：

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL through node name]**:篩選資料，將未通過節點的所有會話過濾掉，以包括通過節點的組維的所有元素。

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL NOT through node name]**:篩選資料，將透過節點傳遞的所有工作階段篩選掉，以包含未傳遞節點的群組維度的所有元素。

![](assets/vis_2DProcessMap_Selections_Movie.png)

![](assets/vis_2DProcessMap_Selections_Page.png)

在3D工藝圖中進行選取時，將圍繞進行選取的節點。 基準會出現在每個列的周圍，協助您比較有無選取的量度值。 請參閱 [了解基準](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).

![](assets/vis_3DProcessMap_Selection.png)
