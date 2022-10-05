---
description: 相依性圖可讓您視覺化並管理設定檔元件的設定。
title: 相依圖
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# 相依圖{#dependency-maps}

{{eol}}

相依性圖可讓您視覺化並管理設定檔元件的設定。

* **資料集元件：** 在資料集的 [!DNL Log Processing.cfg], [!DNL Transformation.cfg]，和 [!DNL dataset include] 檔案。

* **查詢模型元件：** 在Dimension、量度和篩選器資料夾中定義的量度、維度和篩選器。
* **工作區和視覺效果：** 工作區、報表、功能表選項和全域圖層。

如需在相依圖中使用查詢模型元件、工作區和視覺效果的詳細資訊，請參閱 *Data Workbench使用手冊*.

描述檔元件由地圖中的彩色點（節點）表示。 連接節點的線描述相依性，即元件彼此之間的關係。 兩個節點之間的一條線表示左邊節點的一個輸出是右邊節點的一個輸入，即右邊節點取決於左邊節點。

## 顯示資料集元件 {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. 在相依性對應內按一下滑鼠右鍵，然後按一下 **[!UICONTROL Display]**.
1. 選擇 **[!UICONTROL Dataset]**. 左側顯示X [!DNL Dataset].

如需其他顯示選項的詳細資訊，請參閱 *Data Workbench使用手冊*.

下圖顯示的相依性映射的節點代表資料集的日誌源、欄位、轉換和擴展維。

![](assets/vis_DependencyMap.png)

* 黃色 — 綠色節點代表資料集中定義的一或多個記錄來源或篩選器。 日誌源的節點始終位於映射的最左側。
* 灰色節點代表列於 [!DNL Log Processing.cfg] 或 [!DNL Log Processing Include]檔案。

* 藍色節點代表轉換。
* 綠色節點代表延伸維度。

>[!NOTE]
>
>如果您的資料集有單一記錄來源，對應會顯示記錄來源： *日誌源名稱*. 如果您的資料集有多個記錄來源，則會顯示地圖 *數字* 日誌源，其中number是日誌源的計數。 例如，若資料集中有三個記錄來源，您的地圖會顯示3個記錄來源。

如果您看不到地圖上的所有節點，可以移動地圖、放大或縮小以顯示整個地圖，或將焦點放在特定區段。 如需縮放的詳細資訊，請參閱 *Data Workbench使用手冊*.

按一下節點時，將突出顯示依賴該節點的所有節點以及依賴該節點的所有節點，並顯示其名稱。

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>相依圖中醒目顯示的路徑不構成選取項目。

按一下右鍵節點時，您會看到地圖上顯示的每個元件的標識資訊，並選擇菜單選項，以便查看有關該元件的詳細資訊或編輯該元件。 此外，還可以執行文本搜索，並顯示轉換和擴展維的效能資訊。

有關依賴關係映射的這些函式的資訊，請參閱 *Data Workbench使用手冊*.
