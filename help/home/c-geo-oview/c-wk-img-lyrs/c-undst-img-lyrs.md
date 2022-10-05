---
description: 地理設定檔圖層、影像圖層類型和建立新圖層的概念資訊。
title: 瞭解影像層
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# 瞭解影像層{#understanding-imagery-layers}

{{eol}}

地理設定檔圖層、影像圖層類型和建立新圖層的概念資訊。

## 影像層的類型 {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbench [!DNL Geography] 可讓您在data workbench中檢視下列類型的影像層：

* **地形影像層：** 這種層顯示地球的地形影像，可在其中顯示地理資料。 Data Workbench中的地球視覺效果是地形影像層的範例。 請參閱 [使用地形影像層](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **元素點層：** 此類型的圖層會針對一個維度的每個元素在地球上顯示一個點。 請參閱 [使用元素點層](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **向量層：** 此類型的圖層會顯示全球的向量資料（線條圖）。 請參閱 [使用向量層](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

在Data Workbench中，您可以選取要針對特定分析任務顯示的這些層中的哪些層。

## 地理配置檔案層 {#section-4d9fb9b357764493a4d97d2b4068bb67}

此 [!DNL Geography] 設定檔提供一組預設影像層，這些影像層儲存在data workbench伺服器安裝目錄內的「設定檔\地理\地圖」資料夾中：

* **藍色大理石2公里：** 此地形影像層會建立世界的3D地圖，當您將地球視覺效果新增至工作區時，就會顯示這個地圖。 當未選擇此層時，地球不可見，但其他層仍顯示。 此 [!DNL Blue Marble 2km.layer] 檔案引用 [!DNL Blue Marble 2km.tsi] 檔案。

   如需使用全球視覺效果的相關資訊，請參閱 *Data Workbench使用手冊*.

* **郵遞區號：** 此元素點層可讓您使用美國郵遞區號來對應資料集中的位置。 此 [!DNL Zip Points.txt] 查閱檔案(由Adobe提供)包含所有美國郵遞區號和每個郵遞區號的經緯度清單。 此 [!DNL Zip Points.layer] 檔案引用 [!DNL Zip Points.txt] 檔案和 [!DNL Zipcode.dim] 檔案，並包含在全球顯示位置所需的設定參數。 「郵遞區號」維度的每個元素( [!DNL Zipcode.dim])，您在資料集中定義的項目會透過 [!DNL Zip Points.txt] 查閱檔案。

   如需定義維度的相關資訊，請參閱 *資料集設定指南。*

* **邊界：** 這一向量層提供了世界主要政治邊界，如國家，以及地球的自然物理特徵邊界，如湖泊和島嶼。 此 [!DNL Boundaries.layer] 檔案引用一個或多個 [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]，和 [!DNL world boundaries.vec] 檔案。

* **IP座標：** 此元素點層使用動態點，讓您能使用IP位址對應資料集中的位置。 此 [!DNL IP Coordinates.layer] 檔案引用坐標尺寸( [!DNL Coordinates.dim])，並指定「訪客」量度作為度量，以用來決定每個座標的地球點大小。

您的 [!DNL Geography] 安裝中的配置檔案或其他配置檔案可能包含Adobe提供或您公司建立的其他影像層。

## 建立新圖層 {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

您可以複製包含在 [!DNL Geography] 配置檔案到任何配置檔案\*配置檔案名*\映射資料夾，然後根據需要更名和編輯檔案。 所有新層必須滿足以下要求：

* 此 [!DNL .layer] 檔案必須符合其中一種受支援圖層類型的格式。
* 此 [!DNL .layer] 檔案必須參考適當的查閱和維度檔案（如有需要）。
* 參考的查閱檔案也必須儲存在Data Workbench伺服器安裝目錄中，且其路徑必須在 [!DNL .layer] 檔案。

有關每種類型的圖層檔案及其關聯檔案的格式和參數的詳細資訊，請參閱本章中有關相應圖層類型的部分。
