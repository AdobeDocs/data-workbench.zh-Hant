---
description: 資料集組態是指編輯組態檔的程式，其參數可提供資料集建構的規則。
title: 瞭解資料集組態
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
exl-id: 1358d08e-d81c-453d-a3a3-c1f279f38192
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 7%

---

# 瞭解資料集組態{#understanding-dataset-configuration}

{{eol}}

資料集組態是指編輯組態檔的程式，其參數可提供資料集建構的規則。

已建構的資料集實際位於 [!DNL temp.db] 儲存在data workbench伺服器電腦上的檔案，但資料集的組態檔位於設定檔的目錄中。 設定檔包含一組設定檔，可針對特定分析目的建構資料集（包括其延伸維度）。 此外，設定檔包含量度、衍生維度、工作區、報表和視覺效果等實體定義，讓分析師能與資料集互動，並從中取得資訊。

您要編輯的資料集組態檔稱為資料集設定檔。 資料集設定檔會參照多個繼承的設定檔，這些可以是您建立和維護的任何設定檔，讓您可以設定Adobe應用程式以最符合分析需求。 資料集設定檔也可參考Adobe應用程式隨附的內部設定檔，以成為應用程式中所有可用功能的基礎。

如需Adobe應用程式可用的不同設定檔類型的詳細資訊，請參閱 *Data Workbench使用手冊*.

<!--
c_req_config_files.xml
-->

任何Adobe應用程式的資料集設定檔必須包含Insight Server電腦上的下列組態檔：

* **Profile.cfg:** 列出繼承的設定檔和處理伺服器。 處理伺服器是處理設定檔資料的Insight Server DPU。 如果您已安裝Insight Server叢集，則可指定多部Insight Server電腦以執行單一設定檔。

   如需將繼承的設定檔新增至資料集設定檔的指示 [!DNL Profile.cfg] 檔案，請參閱 *《伺服器產品安裝與管理指南》*. 如需安裝Insight Server叢集或設定要在Insight Server叢集上執行的資料集設定檔的相關資訊，請參閱 *《伺服器產品安裝與管理指南》*.

* **Dataset\Log Processing.cfg:** 控制資料集建構程式的記錄處理階段。 請參閱 [記錄處理](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061). 如需 [!DNL Log Processing.cfg] 檔案，請參閱 [記錄處理組態檔](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

* **Dataset\Transformation.cfg:** 控制資料集建構程式的轉換階段。 請參閱 [轉換](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). 此 [!DNL Transformation.cfg] 檔案通常會設定資料集以進行設定檔特定分析。 如需 [!DNL Transformation.cfg] 檔案，請參閱 [轉換組態檔](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

* **資料集包含檔案：** A [!DNL dataset include] 檔案包含 [!DNL Log Processing.cfg] 或 [!DNL Transformation.cfg] 資料集描述檔的檔案，但會在繼承的描述檔中儲存和管理。 [!DNL Dataset include] 檔案會補充主要資料集組態檔。 如需詳細資訊，請參閱 [資料集包含檔案](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

實作Adobe應用程式期間提供給您的資料集設定檔包含一組資料集組態檔，您可以使用 [!DNL Profile Manager].

如需 [!DNL Profile Manager]，請參閱 *Insight使用手冊*.

<!--
c_addl_config_files.xml
-->

雖然並非所有資料集都需要這些檔案，但您可以控制資料集建構程式的其他方面：

* **Log Processing Mode.cfg:** 此 [!DNL Log Processing Mode.cfg] 檔案可讓您暫停將資料處理至資料集、指定離線來源，或指定data workbench伺服器儲存其狀態檔案的頻率。 請參閱 [其他組態檔](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Server.cfg:** 此 [!DNL Server.cfg] 檔案會指定連線至data workbench伺服器之data workbench電腦的預設資料快取大小（以位元組為單位）。 請參閱 [其他組態檔](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Transform.cfg和Transform Mode.cfg :** 只有在您已授權資料轉換功能與您的Adobe應用程式搭配使用時，才能使用這些檔案。 此 [!DNL Transform.cfg] 檔案包含定義日誌源和轉換功能資料轉換的參數。 您定義的轉換操作源資料並將其輸出為您指定的格式。 此 [!DNL Insight Transform Mode.cfg] 檔案可讓您暫停資料集的處理、指定離線來源，或指定Insight Server執行轉換功能儲存其狀態檔案的頻率。 請參閱 [轉換功能](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

<!--
c_next_steps.xml
-->

如需特定資料集設定工作的相關資訊，請使用下表找出並閱讀您感興趣的工作：

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 如果你想…… </th> 
   <th colname="col2" class="entry"> 另請參閱... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>定義記錄來源 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> 記錄來源 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>決定記錄處理期間要輸入資料集的記錄項目 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> 資料篩選</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> 記錄項目條件</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>啟用將追蹤ID與大量事件資料分割 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> 密鑰拆分</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定Insight Server以檔案伺服器單元的形式執行 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 設定Insight Server檔案伺服器單元 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定Insight Server以集中標準化伺服器的形式執行 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 設定Insight Server檔案伺服器單元 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定用於建立時間維度和進行時間轉換的時區 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> 時區 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>小幅變更Adobe提供的內部設定檔所包含的資料集組態檔 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> 編輯現有的資料集包含檔案 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>指定要從記錄處理傳遞到轉換的新資料欄位 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 建立新的資料集包含檔案 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> 記錄處理資料集包含檔案 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>定義轉換 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> 資料轉換 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 建立新的資料集包含檔案 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 轉換資料集包含檔案 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>建立延伸維度 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> 延伸維度 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 建立新的資料集包含檔案 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 轉換資料集包含檔案 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>定義要在整個日誌處理或轉換中使用的參數 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 定義資料集包含檔案中的參數 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>了解可讓您監控或管理資料集的Insight介面 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> 使用資料集組態設定介面 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>隱藏某些延伸維度，使其不會顯示在Insight的維度功能表中 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> 隱藏資料集元件 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在您無法或不想修改的設定檔中覆寫某些資料集組態檔 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> 隱藏資料集元件 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>重新處理資料集 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 重新處理和重新轉換 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>
