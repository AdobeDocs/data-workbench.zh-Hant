---
description: 建立參考查閱檔案以取得經緯度資料的元素點層時，從查閱檔案中擷取每個元素及其相關聯的經緯度，以取得點的位置。
title: 定義參考查閱檔案的元素點層
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 4%

---

# 定義參考查閱檔案的元素點層{#defining-element-point-layers-referencing-lookup-files}

建立參考查閱檔案以取得經緯度資料的元素點層時，從查閱檔案中擷取每個元素及其相關聯的經緯度，以取得點的位置。

您可以使用[!DNL Dynamic Points]功能，取代使用查閱檔案，該功能會將位置的經緯度嵌入維度的每個元素名稱中。 請參閱使用動態點定義元素點層](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)。[

若要定義參照查閱檔案的元素點層，您必須建立或已具備下列功能：

* **在檔** 案或轉換資 [!DNL Transformation.cfg] 料集包含檔案中定義的維。有關轉換配置檔案的資訊，請參閱&#x200B;*資料集配置指南*。

* **一個查** 閱檔案，內含用於繪製每個資料點的資料。此檔案必須至少包含每個資料點的三列資料：鍵、經度和緯度。 如需查閱檔案所需格式的詳細資訊，請參閱[元素點查閱檔案格式](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121)。

* **一個層** 檔案，它指定查閱檔案的位置，並標識相關的維度和度量，以及查閱檔案中的索引鍵、經度和緯度列名稱。有關層檔案所需格式的詳細資訊，請參閱[元素點層檔案格式](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)。

>[!NOTE]
>
>隨[!DNL Geography]設定檔提供的[!DNL Zip Points.layer]檔案是元素點層，可識別[!DNL Zipcode.dim]檔案、[!DNL Sessions.metric]檔案、[!DNL Zip Points.txt]查閱檔案，以及查閱檔案中索引鍵、經度、緯度和名稱欄的名稱。
