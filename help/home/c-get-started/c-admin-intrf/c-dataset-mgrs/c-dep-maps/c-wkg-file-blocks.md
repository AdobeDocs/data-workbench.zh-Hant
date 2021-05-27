---
description: 在相依性圖上顯示資料集元件時，您可以選擇啟用「包含檔案區塊」顯示選項。
title: 檔案區塊
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
exl-id: 04b0faf1-a16d-4e46-b790-5fe2023f2ba1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 1%

---

# 檔案區塊{#file-blocks}

在相依性圖上顯示資料集元件時，您可以選擇啟用「包含檔案區塊」顯示選項。

啟用此選項後，地圖會針對一個資料集配置檔案中定義的所有轉換顯示一個藍色節點，針對一個資料集配置檔案中定義的所有擴展維顯示一個綠色節點。 例如，如果[!DNL log processing dataset include]檔案包含三個轉換的定義，則映射將顯示一個表示這三個轉換的藍色節點。 同樣地，如果[!DNL transformation dataset include]檔案包含兩個擴展維的定義，則映射將顯示一個代表兩個擴展維的綠色節點。

## 轉換塊{#section-c442730394264a0b850792a32eaaa2da}

每個藍色節點都是轉換區塊，並有下列選項：

* 要查看轉換塊的輸入欄位，請按一下右鍵該塊的節點，然後按一下&#x200B;**[!UICONTROL Inputs]**。
* 要查看轉換塊的輸出欄位，請按一下右鍵該塊的節點，然後按一下&#x200B;**[!UICONTROL Outputs]**。
* 要編輯塊中的任何轉換，請按一下右鍵該塊的節點，然後按一下&#x200B;**[!UICONTROL Edit Configuration]**。 顯示的標注包含定義所有轉換的整個配置檔案。 然後，您就可以視需要編輯參數。 如需這些參數的詳細資訊，請參閱&#x200B;*資料集組態指南*。

* 要查看塊中的所有轉換，請按一下右鍵轉換塊的節點，然後按一下&#x200B;**[!UICONTROL Show Details]**。 顯示的標注包含另一個依賴關係映射，顯示塊中所有轉換的節點。

## Dimension塊{#section-0dd581ac6dfc4153bee5300b3cfae2a0}

每個綠色節點都是維度區塊，並有下列選項：

* 要查看維塊的輸入欄位或父維，請按一下右鍵該塊的節點，然後按一下&#x200B;**[!UICONTROL Inputs]**。
* 要查看維塊的輸出維，請按一下右鍵該塊的節點，然後按一下&#x200B;**[!UICONTROL Outputs]**。
