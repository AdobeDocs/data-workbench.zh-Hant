---
description: 當建立參照查閱檔案以取得經緯度資料的元素點層時，從查閱檔案擷取每個元素及其相關的經緯度資料，以取得點的位置。
solution: Analytics
title: 定義元素點層引用查找檔案
topic: Data workbench
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 定義元素點層引用查找檔案{#defining-element-point-layers-referencing-lookup-files}

當建立參照查閱檔案以取得經緯度資料的元素點層時，從查閱檔案擷取每個元素及其相關的經緯度資料，以取得點的位置。

您可以使用功能，而不是使用查 [!DNL Dynamic Points] 閱檔案，功能會將位置的緯度和經度內嵌在維度的每個元素名稱中。 請參 [閱使用動態點定義元素點層](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)。

要定義參照查閱檔案的元素點層，必須建立或已具備以下功能：

* **在檔案** 或轉換資料集 [!DNL Transformation.cfg] 中定義的維包括檔案。 有關轉換配置檔案的資訊，請參 *閱Dataset Configuration Guide*。

* **一個查閱檔案** ，包含用於繪製每個資料點的資料。 此檔案必須至少包含每個資料點的三欄資料：鑰匙，經度和緯度。 如需查閱檔案所需格式的詳細資訊，請參閱「元素點 [查閱檔案格式」](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121)。

* **層檔案** ，它指定查找檔案的位置，並標識查找檔案中的相關維度和度量以及索引鍵、經度和緯度列名。 有關層檔案所需格式的詳細資訊，請參 [閱元素點層檔案格式](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)。

>[!NOTE]
>
>隨配 [!DNL Zip Points.layer] 置檔案提供的檔案是一個元素點層，它標識 [!DNL Geography] 檔案、檔案、 [!DNL Zipcode.dim][!DNL Sessions.metric][!DNL Zip Points.txt] 查閱檔案，以及查閱檔案中鍵、經度、緯度和名稱列的名稱。

