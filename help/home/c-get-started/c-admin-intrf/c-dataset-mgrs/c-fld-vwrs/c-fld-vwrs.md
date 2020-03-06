---
description: 欄位檢視器是包含一或多個資料欄位值的表格。
solution: Analytics
title: 欄位檢視器
topic: Data workbench
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 欄位檢視器{#field-viewer}

欄位檢視器是包含一或多個資料欄位值的表格。

顯示值的欄位是資料集記錄來源、轉換或延伸維度的輸入或輸出。 欄標題中會顯示欄位名稱，而每一列都包含單一來源資料列的欄位值。 由於欄位檢視器可讓您檢視欄位的值，因此在編寫和測試規則運算式時，這些檢視器 [十分有用](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)。

您可以從地圖中以圖說形式或從功能表 [!DNL Transformation Dependency] 中以獨立視覺化形式開啟欄位檢 [!DNL Admin] 視器：

* 從地圖建立欄位檢 [!DNL Transformation Dependency] 視器。 當您從地圖開啟欄位檢視器時， [!DNL Transformation Dependency] 檢視器會根據您按一下滑鼠右鍵的記錄來源、轉換或維度自動填入。 對於日誌源或轉換，查看器中的欄位是日誌源或轉換的輸入或輸出。 對於維度，欄位是維度的輸入。 您可以視需要新增和移除欄位。

* 建立欄位檢視器作為獨立視覺化。 當您將欄位檢視器開啟為獨立的視覺化時，您可以建立 [!DNL Log Processing Field Viewer] 或 [!DNL Transformation Field Viewer]。 檢視器是空白的，您必須將所要的欄位新增至檢視器。 對於 [!DNL Log Processing Field Viewer]，您可以從檔案或任何文 [!DNL Log Processing.cfg] 件添加 [!DNL Log Processing Dataset Include] 欄位。 對於 [!DNL Transformation Field Viewer]，您可以從檔案或任何文 [!DNL Transformation.cfg] 件添加 [!DNL Transformation Dataset Include] 欄位。

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>欄位檢視器不是表格視覺化；因此，它們沒有與表關聯的屬性。

如需新增和移除欄位以及欄位檢視器中篩選的詳細資訊，請參 [閱管理介面](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74)。
