---
description: 在依賴關係圖上顯示資料集元件時，可以啟用「包括檔案塊」顯示選項。
solution: Analytics
title: 檔案塊
topic: Data workbench
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 檔案塊{#file-blocks}

在依賴關係圖上顯示資料集元件時，可以啟用「包括檔案塊」顯示選項。

啟用此選項後，映射將為一個資料集配置檔案中定義的所有轉換顯示一個藍色節點，為一個資料集配置檔案中定義的所有擴展維顯示一個綠色節點。 例如，如果檔案包 [!DNL log processing dataset include] 含三個轉換的定義，則映射將顯示一個表示三個轉換的藍色節點。 同樣地，如果一 [!DNL transformation dataset include] 個檔案包含兩個擴展維的定義，則映射顯示一個代表兩個擴展維的綠色節點。

## 轉換塊 {#section-c442730394264a0b850792a32eaaa2da}

每個藍色節點都是轉換塊，並具有以下選項：

* 要查看轉換塊的輸入欄位，請按一下右鍵該塊的節點，然後按一下 **[!UICONTROL Inputs]**。
* 要查看轉換塊的輸出欄位，請按一下右鍵該塊的節點，然後按一下 **[!UICONTROL Outputs]**。
* 要編輯塊中的任意變形，請按一下右鍵塊的節點，然後按一下 **[!UICONTROL Edit Configuration]**。 顯示的註解包含定義所有轉換的整個配置檔案。 然後，您可以視需要編輯參數。 如需這些參數的詳細資訊，請參閱資料 *集設定指南*。

* 要查看塊中的所有轉換，請按一下右鍵轉換塊的節點，然後按一下 **[!UICONTROL Show Details]**。 顯示的註解包含另一個從屬關係圖，其中顯示塊中所有轉換的節點。

## 尺寸塊 {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

每個綠色節點都是維塊，並具有以下選項：

* 要查看維塊的輸入欄位或父維，請按一下右鍵該塊的節點，然後按一下 **[!UICONTROL Inputs]**。
* 要查看維塊的輸出維，請按一下右鍵該塊的節點，然後按一下 **[!UICONTROL Outputs]**。

