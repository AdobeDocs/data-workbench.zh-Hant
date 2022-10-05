---
description: 影像層的概念資訊。
title: 關於影像層
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 5%

---

# 關於影像層{#about-imagery-layers}

{{eol}}

影像層的概念資訊。

## 影像層類型 {#section-891cbf61e8334690bd203a2bb9761b25}

您可以在Data Workbench中查看以下類型的影像層：

* **[!UICONTROL Terrain image layer]:** 這種層顯示地球的地形影像，可在其中顯示地理資料。 中的地球視覺效果是地形影像層的範例。 請參閱 [使用地形影像層](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** 此類型的圖層會針對一個維度的每個元素在地球上顯示一個點。 請參閱 [使用元素點層](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** 此類型的圖層會顯示全球的向量資料（線條圖）。 請參閱 [使用向量層](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]**&#x200B;使用簡報重疊註解和釐清視覺化。加入圖說文字、箭頭、影像和色彩編碼來突顯和釐清您的資料，並且與其他人共用。

在Data Workbench中，您可以選擇要為特定分析任務顯示的這些圖層中的哪些圖層。

## 地理配置檔案層 {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

此 [!DNL Geography] 配置檔案為您提供了一組預設映像層，這些映像層儲存在Data Workbench伺服器安裝目錄的Profiles\Geography\Maps資料夾中：

* **[!UICONTROL Blue Marble 2km]:** 此地形影像層會建立世界的3D地圖，當您將地球視覺效果新增至工作區時，就會顯示這個地圖。 當未選擇此層時，地球不可見，但其他層仍顯示。 此 [!DNL Blue Marble 2km.layer] 檔案引用 [!DNL Blue Marble 2km.tsi] 檔案。

* **[!UICONTROL Zip Points]:** 此元素點層可讓您使用美國郵遞區號來對應資料集中的位置。 此 [!DNL Zip Points.txt] 查閱檔案(由Adobe提供)包含所有美國郵遞區號和每個郵遞區號的經緯度清單。 此 [!DNL Zip Points.layer] 檔案引用 [!DNL Zip Points.txt] 檔案和 [!DNL Zipcode.dim] 檔案，並包含在全球顯示位置所需的設定參數。 「郵遞區號」維度的每個元素( [!DNL Zipcode.dim])，您在資料集中定義的項目會透過 [!DNL Zip Points.txt] 查閱檔案。

   如需定義維度的相關資訊，請參閱 *資料集組態指南*.

* **[!UICONTROL Boundaries]:** 這一向量層提供了世界主要政治邊界，如國家，以及地球的自然物理特徵邊界，如湖泊和島嶼。 此 [!DNL Boundaries.layer] 檔案引用一個或多個 [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]，和 [!DNL world boundaries.vec] 檔案。

* **[!UICONTROL IP Coordinates]:** 此元素點層使用動態點，讓您能使用IP位址對應資料集中的位置。 此 [!DNL IP Coordinates.layer] 檔案引用坐標尺寸( [!DNL Coordinates.dim])，並指定「訪客」量度作為度量，以用來決定每個座標的地球點大小。

您的 [!UICONTROL NL Geography] 安裝中的配置檔案或其他配置檔案可能包含Adobe提供或您公司建立的其他影像層。

## 建立新圖層 {#section-b5313773316c4e0fa748f7376a8e7f0b}

您可以複製包含在 [!DNL Geography] 配置檔案到任何配置檔案\*配置檔案名*\映射資料夾，然後根據需要更名和編輯檔案。 所有新層必須滿足以下要求：

* 此 [!DNL .layer] 檔案必須符合其中一種受支援圖層類型的格式。
* 此 [!DNL .layer] 檔案必須參考適當的查閱和維度檔案（如有需要）。
* 引用的查找檔案也必須儲存在Data Workbench伺服器安裝目錄中，並且必須在 [!DNL .layer] 檔案。

有關每種類型的圖層檔案及其關聯檔案的格式和參數的詳細資訊，請參閱本章中有關相應圖層類型的部分。
