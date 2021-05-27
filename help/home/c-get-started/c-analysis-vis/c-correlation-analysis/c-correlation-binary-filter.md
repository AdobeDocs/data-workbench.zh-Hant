---
description: 關聯矩陣中的二進位篩選可讓您限制一個或兩個關聯量度的值，以便讓比較更集中。
title: 關聯矩陣中的二進位篩選器
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 5%

---

# 關聯矩陣中的二進位篩選器{#binary-filter-in-the-correlation-matrix}

關聯矩陣中的二進位篩選可讓您限制一個或兩個關聯量度的值，以便讓比較更集中。

要在關聯矩陣上設定二進位篩選器：

1. 在關聯矩陣中，以滑鼠右鍵按一下量度名稱。
1. 選擇&#x200B;**編輯度量詳細資訊**。

   ![](assets/correlation_matrix_binary_filter.png)

   將開啟&#x200B;**[!UICONTROL Edit Correlation Metric Details]**&#x200B;窗口。

   ![](assets/correlation_matrix_metric_details.png)

1. 設定二進位篩選器。

   首先，按一下&#x200B;**[!UICONTROL Inactive]**&#x200B;設定。 它會切換為將篩選器設為&#x200B;**[!UICONTROL Active]**，並顯示&#x200B;**Comparison**&#x200B;和&#x200B;**Value**&#x200B;欄位。

   然後，選取&#x200B;**[!UICONTROL Comparison]**&#x200B;運算子並設定其&#x200B;**[!UICONTROL Value]** ，以設定所選量度的篩選器。

>[!IMPORTANT]
>
>適用於Data Workbench6.2的二進位篩選器已更新為新功能，需要您使用舊版中建置的二進位篩選，來重建任何關聯矩陣。

## 新增Dimension元素{#section-f19f4e0368ca488e92d1e28bcc24417c}

您也可以新增維度元素以限制量度。 量度只能有一個與其相關聯的元素。

![](assets/correlation_matrix_element.png)

在工作區中按一下右鍵，然後選擇&#x200B;**表**。 開啟含有其元素的維度，並拖曳至「編輯關聯量度詳細資料」視窗中的&#x200B;**[!UICONTROL Element]**&#x200B;設定，或拖曳至「關聯矩陣」中的量度。
