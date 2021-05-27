---
description: 您可以從相依性圖中以圖說方式開啟欄位檢視器，或從「管理」功能表以獨立視覺化方式開啟。
title: 建立欄位檢視器
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 2%

---

# 建立欄位檢視器{#create-a-field-viewer}

您可以從相依性圖中以圖說方式開啟欄位檢視器，或從「管理」功能表以獨立視覺化方式開啟。

## 從相依性映射{#section-040cb83c902b49c48b841d35abc127e5}建立欄位檢視器

從相依性映射開啟欄位檢視器時（如[開啟欄位檢視器](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)所示），檢視器會根據您以滑鼠右鍵按一下的記錄來源、轉換或維度自動填入。 對於日誌源或轉換，查看器中的欄位是日誌源或轉換的輸入或輸出。 對於維度，欄位是維度的輸入。 您可以視需要新增和移除欄位。

## 將欄位檢視器建立為獨立視覺效果{#section-11d10e46631d4fdca45d7534336e1e80}

當您以獨立視覺效果形式開啟欄位檢視器時，可以建立[!DNL Log Processing Field Viewer]或[!DNL Transformation Field Viewer]。 檢視器為空白，您必須將所需欄位新增至檢視器。 對於[!DNL Log Processing Field Viewer]，可以添加[!DNL Log Processing.cfg]檔案或任何[!DNL Log Processing dataset include]檔案中的欄位。 對於[!DNL Transformation Field Viewer]，可以添加[!DNL Transformation.cfg]檔案或任何[!DNL Transformation dataset include]檔案中的欄位。

如需有關設定和包含檔案的詳細資訊，請參閱&#x200B;*資料集設定指南*。

## 添加和刪除欄位{#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**向欄位查看器添加欄位**

* 在欄位檢視器內按一下滑鼠右鍵，然後按一下&#x200B;**[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*。

   -或-

* 在欄位檢視器的現有欄內按一下滑鼠右鍵，然後按一下&#x200B;**[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*。

欄位名稱是指欄位的名稱，例項則是指資料集設定中使用欄位的位置，例如資料集處理階段或轉換。 有些欄位會用於資料集設定中的多處（例如，欄位可透過多個轉換修改），因此您必須選取要新增至欄位檢視器的欄位例項。

在可用欄位清單中，檢視器中已顯示之任何欄位的左側會顯示X。

**從欄位檢視器移除欄位**

* 在要刪除的欄內按一下右鍵，然後按一下&#x200B;**[!UICONTROL Remove Field]**。
