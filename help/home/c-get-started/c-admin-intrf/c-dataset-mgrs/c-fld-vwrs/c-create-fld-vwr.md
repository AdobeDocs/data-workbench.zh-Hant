---
description: 您可以從相依性映射中以圖說方式或從「管理」選單以獨立視覺化方式開啟欄位檢視器。
title: 建立欄位檢視器
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 2%

---

# 建立欄位檢視器{#create-a-field-viewer}

您可以從相依性映射中以圖說方式或從「管理」選單以獨立視覺化方式開啟欄位檢視器。

## 從相依性映射{#section-040cb83c902b49c48b841d35abc127e5}建立欄位檢視器

當您從相依性對映開啟欄位檢視器時（如[開啟欄位檢視器](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)所示），檢視器會根據您按一下滑鼠右鍵的記錄來源、轉換或維度自動填入。 對於日誌源或轉換，查看器中的欄位是日誌源或轉換的輸入或輸出。 對於維度，欄位是維度的輸入。 您可以視需要新增和移除欄位。

## 建立欄位檢視器作為獨立的視覺化{#section-11d10e46631d4fdca45d7534336e1e80}

當您將欄位檢視器開啟為獨立的視覺化時，可以建立[!DNL Log Processing Field Viewer]或[!DNL Transformation Field Viewer]。 檢視器是空白的，您必須將所要的欄位新增至檢視器。 對於[!DNL Log Processing Field Viewer]，可以從[!DNL Log Processing.cfg]檔案或任何[!DNL Log Processing dataset include]檔案添加欄位。 對於[!DNL Transformation Field Viewer]，可以從[!DNL Transformation.cfg]檔案或任何[!DNL Transformation dataset include]檔案添加欄位。

有關配置和包含檔案的詳細資訊，請參閱&#x200B;*資料集配置指南*。

## 新增並移除欄位{#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**若要新增欄位至欄位檢視器**

* 在欄位檢視器內按一下滑鼠右鍵，然後按一下&#x200B;**[!UICONTROL Fields]** > ***[!UICONTROL field name]**>* > ***[!UICONTROL instance]**>*。

   -或-

* 在欄位檢視器中，在現有欄位內按一下滑鼠右鍵，然後按一下&#x200B;**[!UICONTROL Fields]** > ***[!UICONTROL field name]**>* > ***[!UICONTROL instance]**>*。

欄位名稱是指欄位的名稱，而例項則指在資料集設定中使用欄位的位置，例如資料集處理階段或轉換。 有些欄位用於資料集設定中的多個位置（例如，欄位可透過多個轉換加以修改），因此您必須選取要新增至欄位檢視器的欄位例項。

在可用欄位清單中，檢視器中已顯示之任何欄位的左側會顯示X。

**從欄位檢視器移除欄位**

* 按一下右鍵要刪除的欄位的列，然後按一下&#x200B;**[!UICONTROL Remove Field]**。
