---
description: 相關性映射使您能夠直觀地顯示和管理配置檔案的元件配置。
title: 相依圖
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 1%

---

# 相依圖{#dependency-maps}

相關性映射使您能夠直觀地顯示和管理配置檔案的元件配置。

* **資料集元件：** 記錄資料集、篩選器、欄位、轉換和在資料集、檔案中定義的 [!DNL Log Processing.cfg]延伸 [!DNL Transformation.cfg]維度 [!DNL dataset include] 。

* **查詢模型元件：** Dimension、量度和篩選器資料夾中定義的量度、維度和篩選器。
* **工作區和視覺化：** 工作區、報表、功能表選項和全球圖層。

有關在相關性映射中使用查詢模型元件、工作區和可視化的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*。

描述檔元件由地圖中的彩色點（節點）表示。 連接節點的線描述了從屬關係，即元件之間如何關聯。 兩個節點之間的一條線表示左側節點的輸出是右側節點的輸入，即右側節點依賴於左側節點。

## 顯示資料集元件{#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. 在相依性映射內按一下右鍵，然後按一下&#x200B;**[!UICONTROL Display]**。
1. 選擇 **[!UICONTROL Dataset]**. [!DNL Dataset]左側出現X。

有關其他顯示選項的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*。

下圖顯示了一個相依性映射，其節點表示資料集的日誌源、欄位、轉換和擴展維。

![](assets/vis_DependencyMap.png)

* 黃色——綠色節點代表資料集中定義的一或多個記錄來源或篩選器。 日誌源的節點始終位於映射中最左側。
* 灰色節點表示列在[!DNL Log Processing.cfg]或[!DNL Log Processing Include]檔案中「欄位」參數中的欄位。

* 藍色節點表示轉換。
* 綠色節點表示擴展維。

>[!NOTE]
>
>如果您的資料集有單一記錄來源，地圖會顯示記錄來源：*日誌源名稱*。 如果您的資料集有多個記錄來源，地圖會顯示&#x200B;*number*&#x200B;記錄來源，其中number是記錄來源的計數。 例如，如果您的資料集中有三個記錄檔來源，您的地圖會顯示3個記錄檔來源。

如果您看不到地圖上的所有節點，可以移動地圖、放大或縮小以顯示整個地圖，或將焦點放在特定區域。 有關縮放的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中的「使用可視化」一章。

按一下某個節點時，依賴該節點的所有節點以及該節點依賴的所有節點都會突出顯示並顯示其名稱。

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>依賴關係映射中突出顯示的路徑不構成選擇。

按一下右鍵某個節點時，可以看到地圖上顯示的每個元件的標識資訊，並選擇菜單選項，以便查看有關該元件或編輯該元件的詳細資訊。 此外，您還可以執行文字搜尋，並顯示轉換和延伸維度的效能資訊。

有關相關性映射的這些函式的資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中的管理介面一章。
