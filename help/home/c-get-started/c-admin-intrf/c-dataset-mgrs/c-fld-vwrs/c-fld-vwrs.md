---
description: 欄位檢視器是包含一或多個資料欄位值的表格。
title: 欄位檢視器
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# 欄位檢視器{#field-viewer}

欄位檢視器是包含一或多個資料欄位值的表格。

顯示值的欄位是資料集記錄來源、轉換或延伸維度的輸入或輸出。 欄標題中會顯示欄位名稱，而每一列都包含單一來源資料列的欄位值。 由於欄位檢視器可讓您檢視欄位的值，因此在編寫和測試[規則運算式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)時，這些值十分有用。

您可以從[!DNL Transformation Dependency]地圖以圖說形式開啟欄位檢視器，或從[!DNL Admin]選單以獨立視覺化形式開啟：

* 從[!DNL Transformation Dependency]地圖建立欄位檢視器。 當您從[!DNL Transformation Dependency]地圖開啟欄位檢視器時，檢視器會根據您按一下滑鼠右鍵的記錄來源、轉換或維度自動填入。 對於日誌源或轉換，查看器中的欄位是日誌源或轉換的輸入或輸出。 對於維度，欄位是維度的輸入。 您可以視需要新增和移除欄位。

* 建立欄位檢視器作為獨立視覺化。 當您將欄位檢視器開啟為獨立的視覺化時，可以建立[!DNL Log Processing Field Viewer]或[!DNL Transformation Field Viewer]。 檢視器是空白的，您必須將所要的欄位新增至檢視器。 對於[!DNL Log Processing Field Viewer]，可以從[!DNL Log Processing.cfg]檔案或任何[!DNL Log Processing Dataset Include]檔案添加欄位。 對於[!DNL Transformation Field Viewer]，可以從[!DNL Transformation.cfg]檔案或任何[!DNL Transformation Dataset Include]檔案添加欄位。

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>欄位檢視器不是表格視覺化；因此，它們沒有與表關聯的屬性。

有關在欄位查看器中添加和刪除欄位和篩選的資訊，請參閱[管理介面](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74)。
