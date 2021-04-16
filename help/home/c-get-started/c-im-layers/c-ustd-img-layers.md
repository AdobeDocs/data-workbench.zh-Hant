---
description: 影像圖層的概念性資訊。
title: 關於影像層
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 5%

---

# 關於影像層{#about-imagery-layers}

影像圖層的概念性資訊。

## 影像圖層類型{#section-891cbf61e8334690bd203a2bb9761b25}

您可以在Data Workbench中檢視下列類型的影像圖層：

* **[!UICONTROL Terrain image layer]:** 此類型的圖層顯示地球的地形影像，可在其中顯示地理資料。其中的全球可視化是地形影像層的一個實例。 請參閱[使用地形圖層](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)。

* **[!UICONTROL Element point layer]:** 此類型的圖層會在球體上為尺寸的每個元素顯示一個點。請參閱[使用元素點圖層](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd)。

* **[!UICONTROL Vector layer]:** 此類型的圖層會在全球顯示向量資料（線條圖）。請參閱[使用向量圖層](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9)。

* **[!UICONTROL Presentation layer]**&#x200B;使用簡報重疊註解和釐清視覺化。加入圖說文字、箭頭、影像和色彩編碼來突顯和釐清您的資料，並且與其他人共用。

在Data Workbench中，您可以選擇要為特定分析任務顯示的這些圖層。

## 地理位置描述檔圖層{#section-d04ab9f1a8cd4c6580e48ce44ac51898}

[!DNL Geography]描述檔提供一組預設影像圖層，這些圖層儲存在Profiles\Geography\Maps folder within the Data Workbench server installation directory目錄中：

* **[!UICONTROL Blue Marble 2km]:** 此地形影像圖層會建立世界的3-D地圖，當您將全球視覺化新增至工作區時，就會顯示此地圖。如果未選取此圖層，地球不可見，但仍會顯示其他圖層。 [!DNL Blue Marble 2km.layer]檔案引用[!DNL Blue Marble 2km.tsi]檔案。

* **[!UICONTROL Zip Points]:** 此元素點層可讓您使用美國郵遞區號來對應資料集中的位置。[!DNL Zip Points.txt]查閱檔案(由Adobe提供)包含所有美國郵遞區號和每個郵遞區號的經緯度清單。 [!DNL Zip Points.layer]檔案會參照[!DNL Zip Points.txt]檔案和[!DNL Zipcode.dim]檔案，並包含顯示全球位置所需的組態參數。 您在資料集中定義的郵遞區號維度([!DNL Zipcode.dim])的每個元素，都會使用[!DNL Zip Points.txt]查閱檔案中該郵遞區號的經緯度，在全球進行對應。

   有關定義維的資訊，請參閱&#x200B;*資料集配置指南*。

* **[!UICONTROL Boundaries]:** 此向量層提供了世界主要政治邊界，如國家，以及地球的自然物理特徵邊界，如湖泊和島嶼。[!DNL Boundaries.layer]檔案引用一個或多個[!DNL mwcoast.vec]、[!DNL mwisland.vec]、[!DNL mwlake.vec]、[!DNL mwnation.vec]、[!DNL mwriver.vec]、[!DNL mwstate.vec]、[!DNL US states.vec]和[!DNL world boundaries.vec]檔案。

* **[!UICONTROL IP Coordinates]:** 此元素點層使用動態點，讓您使用IP位址映射資料集中的位置。[!DNL IP Coordinates.layer]檔案會參照坐標維度([!DNL Coordinates.dim])，並指定「訪客」量度作為度量，用以決定每個坐標的全球點大小。

您的[!UICONTROL NL Geography]描述檔或安裝中的其他描述檔可能包含Adobe提供或您的公司建立的其他影像圖層。

## 建立新層{#section-b5313773316c4e0fa748f7376a8e7f0b}

您可以將[!DNL Geography]描述檔中包含的適當圖層檔案類型複製到任何「描述檔」\*描述檔名稱*\Maps檔案夾，然後視需要重新命名和編輯檔案，以建立新的影像圖層。 所有新圖層都必須符合下列需求：

* [!DNL .layer]檔案必須符合其中一種支援圖層類型的格式。
* 如有必要，[!DNL .layer]檔案必須參考適當的查閱和維度檔案。
* 參考的查閱檔案也必須儲存在Data Workbench伺服器安裝目錄中，而且其路徑必須在[!DNL .layer]檔案中正確指定。

有關每種類型圖層檔案及其關聯檔案的格式和參數的詳細資訊，請參閱本章中有關相應圖層類型的章節。
