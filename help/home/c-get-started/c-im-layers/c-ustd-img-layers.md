---
description: 影像圖層的概念性資訊。
solution: Analytics
title: 關於影像圖層
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 關於影像圖層{#about-imagery-layers}

影像圖層的概念性資訊。

## 影像圖層類型 {#section-891cbf61e8334690bd203a2bb9761b25}

您可以在資料工作台中檢視下列類型的影像圖層：

* **[!UICONTROL Terrain image layer]:**這種層顯示地球的地形影像，可在其中顯示地理資料。 其中的全球可視化是地形影像層的一個實例。 請參[閱使用地形圖層](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)。

* **[!UICONTROL Element point layer]:**此類型的圖層會在球體上為尺寸的每個元素顯示一個點。 請參[閱使用元素點層](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd)。

* **[!UICONTROL Vector layer]:**此類圖層會在全球顯示向量資料（線條圖）。 請參[閱使用向量圖層](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9)。

* **[!UICONTROL Presentation layer]**&#x200B;使用簡報重疊註解和釐清視覺化。加入圖說文字、箭頭、影像和色彩編碼來突顯和釐清您的資料，並且與其他人共用。

在「資料工作台」中，您可以選取要針對特定分析任務顯示的這些圖層。

## 地理描述檔圖層 {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

此 [!DNL Geography] 描述檔提供一組預設影像圖層，這些圖層儲存在Profiles\Geography\Maps folder within the Data Workbench server installation directory目錄中：

* **[!UICONTROL Blue Marble 2km]:**此地形影像圖層可建立世界的3-D地圖，當您將全球視覺化新增至工作區時，就會顯示此地圖。 如果未選取此圖層，地球不可見，但仍會顯示其他圖層。 檔案[!DNL Blue Marble 2km.layer]引用該文[!DNL Blue Marble 2km.tsi]件。

* **[!UICONTROL Zip Points]:**此元素點層可讓您使用美國郵遞區號來對應資料集中的位置。 查[!DNL Zip Points.txt]閱檔案（由Adobe提供）包含所有美國郵遞區號和每個郵遞區號的經緯度清單。 文[!DNL Zip Points.layer]件引用文[!DNL Zip Points.txt]件和文[!DNL Zipcode.dim]件，並包含顯示全局位置所需的配置參數。 您在資料集中定義的「郵遞區號」維度([!DNL Zipcode.dim])的每個元素，都會使用查閱檔案中該「郵遞區號」的經緯度，在全球[!DNL Zip Points.txt]上對應。

   如需定義維度的詳細資訊，請參閱資 *料集設定指南*。

* **[!UICONTROL Boundaries]:**這一向量層提供了世界主要政治邊界，如國家，以及地球的自然物理特徵邊界，如湖泊和島嶼。 文[!DNL Boundaries.layer]件引用一個或多個檔案、、[!DNL mwcoast.vec]、、[!DNL mwisland.vec]、和[!DNL mwlake.vec][!DNL mwnation.vec][!DNL mwriver.vec][!DNL mwstate.vec][!DNL US states.vec][!DNL world boundaries.vec],

* **[!UICONTROL IP Coordinates]:**此元素點層使用動態點，讓您使用IP位址來映射資料集中的位置。 檔[!DNL IP Coordinates.layer]案會參照座標維度([!DNL Coordinates.dim])，並指定「訪客」量度作為量度，用以決定每個座標的全球點大小。

您的 [!UICONTROLNL 地理位置] 、設定檔或安裝中的其他設定檔可能包含Adobe或您的公司所建立的其他影像圖層。

## Create a new layer {#section-b5313773316c4e0fa748f7376a8e7f0b}

您可以將描述檔中包含的適當類型圖層檔案複製到任何「描述檔」\*描述檔名稱*\Maps檔案夾，然後視需要重新命名和編輯檔案，以建立新的影像圖層。 [!DNL Geography] 所有新圖層都必須符合下列需求：

* 文 [!DNL .layer] 件必須遵循其中一種支援的圖層類型的格式。
* 檔 [!DNL .layer] 案必要時，必須參考適當的查閱和維度檔案。
* 參考的查閱檔案也必須儲存在資料工作台伺服器安裝目錄中，而且必須在檔案中正確指定其路 [!DNL .layer] 徑。

有關每種類型圖層檔案及其關聯檔案的格式和參數的詳細資訊，請參閱本章中有關相應圖層類型的章節。
