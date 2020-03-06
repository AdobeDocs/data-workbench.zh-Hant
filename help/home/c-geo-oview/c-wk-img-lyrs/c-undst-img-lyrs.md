---
description: 「地理」描述檔圖層、影像圖層類型以及建立新圖層的概念性資訊。
solution: Analytics
title: 瞭解影像圖層
topic: Data workbench
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 瞭解影像圖層{#understanding-imagery-layers}

「地理」描述檔圖層、影像圖層類型以及建立新圖層的概念性資訊。

## 影像圖層類型 {#section-ce25364651a04cd1b83f9ac7c231fa41}

資料工 [!DNL Geography] 作台可讓您在資料工作台中檢視下列類型的影像圖層：

* **地形圖層：** 這種層顯示地球的地形影像，可在其中顯示地理資料。 資料工作台中的全球可視化是地形影像層的一個實例。 請參 [閱使用地形圖層](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)。

* **元素點層：** 此類型的圖層會在球體上為尺寸的每個元素顯示一個點。 請參 [閱使用元素點層](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9)。

* **向量圖層：** 此類圖層會在全球顯示向量資料（線條圖）。 請參 [閱使用向量圖層](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620)。

在資料工作台中，您可以選取要針對特定分析工作顯示的這些圖層。

## 地理設定檔圖層 {#section-4d9fb9b357764493a4d97d2b4068bb67}

此 [!DNL Geography] 描述檔提供一組預設影像圖層，這些圖層儲存在Profiles\Geography\Maps folder within the data workbench server installation directory目錄中：

* **藍色大理石2公里：** 此地形影像圖層可建立世界的3-D地圖，當您將全球視覺化新增至工作區時，就會顯示此地圖。 如果未選取此圖層，地球不可見，但仍會顯示其他圖層。 檔案 [!DNL Blue Marble 2km.layer] 引用該文 [!DNL Blue Marble 2km.tsi] 件。

   如需使用全球視覺化的詳細資訊，請參閱「資 *料工作台使用指南」*。

* **郵遞區號：** 此元素點層可讓您使用美國郵遞區號來對應資料集中的位置。 查 [!DNL Zip Points.txt] 閱檔案（由Adobe提供）包含所有美國郵遞區號和每個郵遞區號的經緯度清單。 文 [!DNL Zip Points.layer] 件引用文 [!DNL Zip Points.txt] 件和文 [!DNL Zipcode.dim] 件，並包含顯示全局位置所需的配置參數。 您在資料集中定義的「郵遞區號」維度( [!DNL Zipcode.dim])的每個元素，都會使用查閱檔案中該「郵遞區號」的經緯度，在全球 [!DNL Zip Points.txt] 上對應。

   如需定義維度的詳細資訊，請參閱資 *料集設定指南。*

* **邊界：** 這一向量層提供了世界主要政治邊界，如國家，以及地球的自然物理特徵邊界，如湖泊和島嶼。 文 [!DNL Boundaries.layer] 件引用一個或多個檔案、、 [!DNL mwcoast.vec]、、 [!DNL mwisland.vec]、和 [!DNL mwlake.vec][!DNL mwnation.vec][!DNL mwriver.vec][!DNL mwstate.vec][!DNL US states.vec][!DNL world boundaries.vec] ,

* **IP座標：** 此元素點層使用動態點，讓您使用IP位址來映射資料集中的位置。 檔 [!DNL IP Coordinates.layer] 案會參照座標維度( [!DNL Coordinates.dim])，並指定「訪客」量度作為量度，用以決定每個座標的全球點大小。

您的 [!DNL Geography] 設定檔或安裝中的其他設定檔可能包含Adobe或您的公司所建立的其他影像圖層。

## 建立新圖層 {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

您可以將描述檔中包含的適當類型圖層檔案複製到任何「描述檔」\*描述檔名稱*\Maps檔案夾，然後視需要重新命名和編輯檔案，以建立新的影像圖層。 [!DNL Geography] 所有新圖層都必須符合下列需求：

* 文 [!DNL .layer] 件必須遵循其中一種支援的圖層類型的格式。
* 檔 [!DNL .layer] 案必要時，必須參考適當的查閱和維度檔案。
* 參考的查閱檔案也必須儲存在資料工作台伺服器安裝目錄中，而且必須在檔案中正確指定其路 [!DNL .layer] 徑。

有關每種類型圖層檔案及其關聯檔案的格式和參數的詳細資訊，請參閱本章中有關相應圖層類型的章節。
