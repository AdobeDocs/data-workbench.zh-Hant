---
description: 「地理」描述檔圖層、影像圖層類型以及建立新圖層的概念性資訊。
title: 瞭解影像層
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# 瞭解影像層{#understanding-imagery-layers}

「地理」描述檔圖層、影像圖層類型以及建立新圖層的概念性資訊。

## 影像圖層類型{#section-ce25364651a04cd1b83f9ac7c231fa41}

資料工作台[!DNL Geography]可讓您在資料工作台中檢視下列類型的影像圖層：

* **地形影像層：** 這種類型的地形圖層顯示地球的地形影像，可以顯示地理資料。資料工作台中的全球可視化是地形影像層的一個實例。 請參閱[使用地形圖層](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)。

* **元素點層：** 此類型的圖層會在球體上為尺寸的每個元素顯示一個點。請參閱[使用元素點圖層](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9)。

* **向量圖層：** 此類型的圖層會在地球上顯示向量資料（線條圖）。請參閱[使用向量圖層](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620)。

在資料工作台中，您可以選取要針對特定分析工作顯示的這些圖層。

## 地理設定檔圖層{#section-4d9fb9b357764493a4d97d2b4068bb67}

[!DNL Geography]描述檔提供一組預設影像圖層，這些圖層儲存在Profiles\Geography\Maps folder within the data workbench server installation directory目錄中：

* **藍色大理石2km:** 此地形影像圖層可建立世界的3-D地圖，當您將全球視覺化加入工作區時，就會顯示此地圖。如果未選取此圖層，地球不可見，但仍會顯示其他圖層。 [!DNL Blue Marble 2km.layer]檔案引用[!DNL Blue Marble 2km.tsi]檔案。

   如需使用全球視覺化的詳細資訊，請參閱&#x200B;*Data Workbench使用指南*。

* **郵遞區號：** 此元素點層可讓您使用美國郵遞區號來對應資料集中的位置。[!DNL Zip Points.txt]查閱檔案(由Adobe提供)包含所有美國郵遞區號和每個郵遞區號的經緯度清單。 [!DNL Zip Points.layer]檔案會參照[!DNL Zip Points.txt]檔案和[!DNL Zipcode.dim]檔案，並包含顯示全球位置所需的組態參數。 您在資料集中定義的郵遞區號維度([!DNL Zipcode.dim])的每個元素，都會使用[!DNL Zip Points.txt]查閱檔案中該郵遞區號的經緯度，在全球進行對應。

   有關定義維的資訊，請參閱&#x200B;*資料集配置指南。*

* **邊界：** 此向量層提供世界主要政治邊界，例如國家，以及地球的自然物理特徵邊界，如湖泊和島嶼。[!DNL Boundaries.layer]檔案引用一個或多個[!DNL mwcoast.vec]、[!DNL mwisland.vec]、[!DNL mwlake.vec]、[!DNL mwnation.vec]、[!DNL mwriver.vec]、[!DNL mwstate.vec]、[!DNL US states.vec]和[!DNL world boundaries.vec]檔案。

* **IP座標：** 此元素點層使用動態點，讓您使用IP位址來對應資料集中的位置。[!DNL IP Coordinates.layer]檔案會參照坐標維度([!DNL Coordinates.dim])，並指定「訪客」量度作為度量，用以決定每個坐標的全球點大小。

您的[!DNL Geography]描述檔或安裝中的其他描述檔可能包含Adobe提供或您的公司建立的其他影像圖層。

## 建立新層{#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

您可以將[!DNL Geography]描述檔中包含的適當圖層檔案類型複製到任何「描述檔」\*描述檔名稱*\Maps檔案夾，然後視需要重新命名和編輯檔案，以建立新的影像圖層。 所有新圖層都必須符合下列需求：

* [!DNL .layer]檔案必須符合其中一種支援圖層類型的格式。
* 如有必要，[!DNL .layer]檔案必須參考適當的查閱和維度檔案。
* 參考的查閱檔案也必須儲存在資料工作台伺服器安裝目錄中，而且其路徑必須在[!DNL .layer]檔案中正確指定。

有關每種類型圖層檔案及其關聯檔案的格式和參數的詳細資訊，請參閱本章中有關相應圖層類型的章節。
