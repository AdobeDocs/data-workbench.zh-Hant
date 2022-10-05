---
description: 建立參考查閱檔案以取得經緯度資料的元素點層時，從查閱檔案中擷取每個元素及其相關聯的經緯度，以取得點的位置。
title: 定義參考查閱檔案的元素點層
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 4%

---

# 定義參考查閱檔案的元素點層{#defining-element-point-layers-referencing-lookup-files}

{{eol}}

建立參考查閱檔案以取得經緯度資料的元素點層時，從查閱檔案中擷取每個元素及其相關聯的經緯度，以取得點的位置。

您可以使用 [!DNL Dynamic Points] 功能，會將位置的經緯度內嵌在維度的每個元素名稱中。 請參閱 [使用動態點定義元素點層](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

若要定義參照查閱檔案的元素點層，您必須建立或已具備下列功能：

* **維度** 在 [!DNL Transformation.cfg] 檔案或轉換資料集包含檔案。 如需轉換組態檔的相關資訊，請參閱 *資料集組態指南*.

* **查閱檔案** 包含用於繪製每個資料點的資料。 此檔案必須至少包含每個資料點的三列資料：鍵、經度和緯度。 如需查閱檔案所需格式的詳細資訊，請參閱 [元素點查閱檔案格式](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **圖層檔案** 這會指定查閱檔案的位置，並識別相關的維度和量度，以及查閱檔案中的索引鍵、經度和緯度欄名稱。 有關所需圖層檔案格式的詳細資訊，請參見 [元素點層檔案格式](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>此 [!DNL Zip Points.layer] 檔案，隨 [!DNL Geography] 設定檔是可識別 [!DNL Zipcode.dim] 檔案， [!DNL Sessions.metric] 檔案， [!DNL Zip Points.txt] 查閱檔案，以及查閱檔案中索引鍵、經度、緯度和名稱欄的名稱。
