---
description: 地理設定檔圖層、影像圖層類型和建立新圖層的概念資訊。
title: 瞭解影像層
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# 瞭解影像層{#understanding-imagery-layers}

地理設定檔圖層、影像圖層類型和建立新圖層的概念資訊。

## 影像層類型{#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbench [!DNL Geography]可讓您在Data Workbench中檢視下列類型的影像層：

* **地形影像層：** 此類型的層顯示地球的地形影像，可在其上顯示地理資料。Data Workbench中的地球視覺效果是地形影像層的範例。 請參閱[使用地形影像層](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)。

* **元素點層：** 此類型的層會針對一個維度的每個元素在地球上顯示一個點。請參閱[使用元素點層](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9)。

* **向量層：** 此類型的層會在地球上顯示向量資料（線條圖）。請參閱[使用向量層](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620)。

在Data Workbench中，您可以選取要針對特定分析任務顯示的這些層中的哪些層。

## 地理配置檔案層{#section-4d9fb9b357764493a4d97d2b4068bb67}

[!DNL Geography]配置檔案提供一組預設影像層，這些圖層儲存在Profiles\Geography\Maps folder within the data workbench server installation directory中：

* **藍色大理石2公里：** 此地形影像層會建立世界的3D地圖，當您將地球視覺效果新增至工作區時，就會顯示這些地圖。當未選擇此層時，地球不可見，但其他層仍顯示。 [!DNL Blue Marble 2km.layer]檔案引用[!DNL Blue Marble 2km.tsi]檔案。

   如需使用全域視覺效果的相關資訊，請參閱&#x200B;*Data Workbench使用手冊*。

* **郵遞區號：** 此元素點層可讓您使用美國郵遞區號來對應資料集中的位置。[!DNL Zip Points.txt]查閱檔案(由Adobe提供)包含所有美國郵遞區號和每個郵遞區號的經緯度清單。 [!DNL Zip Points.layer]檔案引用[!DNL Zip Points.txt]檔案和[!DNL Zipcode.dim]檔案，並包含在全局上顯示位置所需的配置參數。 您在資料集中定義的「郵遞區號」維度([!DNL Zipcode.dim])的每個元素，都會透過[!DNL Zip Points.txt]查閱檔案中該郵遞區號所列的經緯度，在全球上對應。

   如需定義維度的相關資訊，請參閱&#x200B;*資料集設定指南。*

* **邊界：** 此向量層提供世界主要政治邊界，例如國家，以及地球的自然物理特徵邊界，例如湖泊和島嶼。[!DNL Boundaries.layer]檔案引用了[!DNL mwcoast.vec]、[!DNL mwisland.vec]、[!DNL mwlake.vec]、[!DNL mwnation.vec]、[!DNL mwriver.vec]、[!DNL mwstate.vec]、[!DNL US states.vec]和[!DNL world boundaries.vec]檔案中的一個或多個。

* **IP座標：** 此元素點層使用動態點，讓您使用IP位址對應資料集中的位置。[!DNL IP Coordinates.layer]檔案會參考座標維度([!DNL Coordinates.dim])，並指定訪客量度作為度量，以用來決定每個座標的地球上點的大小。

您的[!DNL Geography]配置檔案或安裝中的其他配置檔案可能包含Adobe提供或您的公司建立的其他影像層。

## 建立新層{#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

通過將[!DNL Geography]配置檔案中包含的適當類型的圖層檔案複製到任何「配置檔案」\*配置檔案名稱*\Maps資料夾中，然後根據需要更名和編輯檔案，可以建立新的影像層。 所有新層必須滿足以下要求：

* [!DNL .layer]檔案必須符合其中一個受支援圖層類型的格式。
* 必要時，[!DNL .layer]檔案必須參考適當的查閱和維度檔案。
* 參考的查閱檔案也必須儲存在Data Workbench伺服器安裝目錄中，且其路徑必須在[!DNL .layer]檔案中正確指定。

有關每種類型的圖層檔案及其關聯檔案的格式和參數的詳細資訊，請參閱本章中有關相應圖層類型的部分。
