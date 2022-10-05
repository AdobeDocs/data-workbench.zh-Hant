---
description: 欄位檢視器是包含一或多個資料欄位值的表格。
title: 欄位檢視器
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# 欄位檢視器{#field-viewer}

{{eol}}

欄位檢視器是包含一或多個資料欄位值的表格。

顯示值的欄位是資料集記錄來源、轉換或延伸維度的輸入或輸出。 欄標題中顯示欄位名稱，每一列包含單一來源資料列的欄位值。 由於欄位檢視器可讓您查看欄位的值，因此在撰寫和測試時很有幫助 [規則運算式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

您可以從 [!DNL Transformation Dependency] 從 [!DNL Admin] 功能表：

* 從 [!DNL Transformation Dependency] 地圖。 當您從 [!DNL Transformation Dependency] 地圖中，檢視器會根據您按一下滑鼠右鍵的記錄來源、轉換或維度自動填入。 對於日誌源或轉換，查看器中的欄位是日誌源或轉換的輸入或輸出。 對於維度，欄位是維度的輸入。 您可以視需要新增和移除欄位。

* 將欄位檢視器建立為獨立視覺效果。 當您以獨立視覺效果形式開啟欄位檢視器時，可以建立 [!DNL Log Processing Field Viewer] 或 [!DNL Transformation Field Viewer]. 檢視器為空白，您必須將所需欄位新增至檢視器。 若 [!DNL Log Processing Field Viewer]，您可以從 [!DNL Log Processing.cfg] 檔案或任何 [!DNL Log Processing Dataset Include] 檔案。 若 [!DNL Transformation Field Viewer]，您可以從 [!DNL Transformation.cfg] 檔案或任何 [!DNL Transformation Dataset Include] 檔案。

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>欄位檢視器不是表格視覺效果；因此，它們沒有與表關聯的屬性。

如需新增和移除欄位以及在欄位檢視器中篩選的相關資訊，請參閱 [管理介面](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
