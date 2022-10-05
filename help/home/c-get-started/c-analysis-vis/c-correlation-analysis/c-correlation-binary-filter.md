---
description: 關聯矩陣中的二進位篩選可讓您限制一個或兩個關聯量度的值，以便讓比較更集中。
title: 關聯矩陣中的二進位篩選器
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 5%

---

# 關聯矩陣中的二進位篩選器{#binary-filter-in-the-correlation-matrix}

{{eol}}

關聯矩陣中的二進位篩選可讓您限制一個或兩個關聯量度的值，以便讓比較更集中。

要在關聯矩陣上設定二進位篩選器：

1. 在關聯矩陣中，以滑鼠右鍵按一下量度名稱。
1. 選擇 **編輯量度詳細資料**.

   ![](assets/correlation_matrix_binary_filter.png)

   此 **[!UICONTROL Edit Correlation Metric Details]** 窗口。

   ![](assets/correlation_matrix_metric_details.png)

1. 設定二進位篩選器。

   首先，按一下 **[!UICONTROL Inactive]** 設定。 它會切換為 **[!UICONTROL Active]** 並顯示 **比較** 和 **值** 欄位。

   然後，選取 **[!UICONTROL Comparison]** 運算子和設定其 **[!UICONTROL Value]** 來設定所選量度的篩選。

>[!IMPORTANT]
>
>適用於Data Workbench6.2的二進位篩選器已更新為新功能，需要您使用舊版中建置的二進位篩選，來重建任何關聯矩陣。

## 新增Dimension元素 {#section-f19f4e0368ca488e92d1e28bcc24417c}

您也可以新增維度元素以限制量度。 量度只能有一個與其相關聯的元素。

![](assets/correlation_matrix_element.png)

在工作區中按一下滑鼠右鍵，然後選取 **表格**. 開啟含有其元素的維度，並拖曳至 **[!UICONTROL Element]** 在「編輯關聯度量詳細資料」視窗中設定，或在「關聯矩陣」中拖放度量。
