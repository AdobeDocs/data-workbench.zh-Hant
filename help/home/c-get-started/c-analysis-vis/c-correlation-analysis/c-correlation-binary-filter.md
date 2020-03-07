---
description: 關聯矩陣中的二進位篩選可讓您限制其中一個或兩個關聯度量的值，以便更專注比較。
solution: Analytics
title: 關聯矩陣中的二值濾波
topic: Data workbench
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 關聯矩陣中的二值濾波{#binary-filter-in-the-correlation-matrix}

關聯矩陣中的二進位篩選可讓您限制其中一個或兩個關聯度量的值，以便更專注比較。

若要在關聯矩陣上設定二進位篩選：

1. 在關聯矩陣中，以滑鼠右鍵按一下量度名稱。
1. 選取「 **編輯量度詳細資訊**」。

   ![](assets/correlation_matrix_binary_filter.png)

   窗 **[!UICONTROL Edit Correlation Metric Details]** 戶將開啟。

   ![](assets/correlation_matrix_metric_details.png)

1. 設定二進位篩選。

   首先，按一下 **[!UICONTROL Inactive]** 設定。 它會切換，將篩選設為 **[!UICONTROL Active]** 並顯示「比 **較** 」和 **「值** 」欄位。

   然後，選取運 **[!UICONTROL Comparison]** 算子並設定其 **[!UICONTROL Value]** 以設定所選量度的篩選。

>[!IMPORTANT]
>
>資料工作台6.2的二進位篩選已更新，並具備新功能，您必須使用舊版中建立的二進位篩選來重建任何關聯矩陣。

## 添加維元素 {#section-f19f4e0368ca488e92d1e28bcc24417c}

您也可以新增維度元素來限制量度。 量度只能有一個與其關聯的元素。

![](assets/correlation_matrix_element.png)

在工作區中按一下滑鼠右鍵，然後選取「 **表格」**。 開啟含其元素的維度，並拖曳至「編輯關聯度量詳 **[!UICONTROL Element]** 細資料」視窗中的設定，或拖曳至關聯矩陣中的度量。
