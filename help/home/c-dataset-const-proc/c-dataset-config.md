---
description: 資料集配置是指編輯配置檔案的過程，其參數為資料集構建提供了規則。
title: 瞭解資料集組態
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
exl-id: 1358d08e-d81c-453d-a3a3-c1f279f38192
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 7%

---

# 瞭解資料集組態{#understanding-dataset-configuration}

資料集配置是指編輯配置檔案的過程，其參數為資料集構建提供了規則。

所構造的資料集實際駐留在資料工作台伺服器電腦上儲存的[!DNL temp.db]檔案中，但資料集的配置檔案駐留在配置檔案的目錄中。 描述檔包含一組設定檔，用以建構資料集（包括其延伸維度）以用於特定分析用途。 此外，描述檔包含量度、衍生維度、工作區、報表和視覺化等實體的定義，讓分析者能與資料集互動並從中取得資訊。

您要編輯的資料集設定檔稱為資料集設定檔。 資料集描述檔會參考多個繼承的描述檔，這些描述檔可以是您建立和維護的任何描述檔，以便您能夠設定Adobe應用程式以最符合您的分析需求。 資料集描述檔也可以參考您的Adobe應用程式所提供的內部描述檔，以構成應用程式中所有可用功能的基礎。

有關Adobe應用程式可用的不同類型配置檔案的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*。

<!--
c_req_config_files.xml
-->

任何Adobe應用程式的資料集描述檔必須包含Insight Server機器上的下列設定檔案：

* **Profile.cfg：列** 出繼承的配置檔案和處理伺服器。處理伺服器是Insight Server DPU，可處理描述檔的資料。 如果您已安裝Insight Server叢集，可以指定多部Insight Server電腦以執行單一描述檔。

   有關將繼承的配置檔案添加到資料集配置檔案的[!DNL Profile.cfg]檔案的說明，請參閱&#x200B;*伺服器產品安裝和管理指南*。 如需有關安裝Insight Server叢集或設定資料集設定檔以在Insight Server叢集上執行的詳細資訊，請參閱&#x200B;*伺服器產品安裝與管理指南*。

* **Dataset\Log Processing.cfg：控** 制資料集建構程式的記錄處理階段。請參閱[記錄處理](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061)。 有關[!DNL Log Processing.cfg]檔案的詳細資訊，請參閱[日誌處理配置檔案](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)。

* **Dataset\Transformation.cfg：控** 制資料集構建過程的轉換階段。請參閱[轉換](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda)。 [!DNL Transformation.cfg]檔案通常會設定資料集以進行描述檔特定分析。 有關[!DNL Transformation.cfg]檔案的詳細資訊，請參閱[轉換配置檔案](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)。

* **資料集包含檔** 案： [!DNL dataset include] 檔案包含資料集描述檔或檔案中所包含參數的 [!DNL Log Processing.cfg] 子集，但會儲存並管理在繼承的描 [!DNL Transformation.cfg] 述檔中。[!DNL Dataset include] 檔案補充主資料集配置檔案。如需詳細資訊，請參閱[資料集包含檔案](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

在實作Adobe應用程式期間提供給您的資料集描述檔包含一組資料集設定檔，您可使用[!DNL Profile Manager]來開啟、編輯和儲存。

如需[!DNL Profile Manager]的詳細資訊，請參閱&#x200B;*Insight使用指南*。

<!--
c_addl_config_files.xml
-->

雖然並非所有資料集都需要這些檔案，但這些檔案可讓您控制資料集建構程式的其他方面：

* **記錄處理模式。cfg:** 檔 [!DNL Log Processing Mode.cfg] 案可讓您暫停資料集中的資料處理、指定離線來源，或指定資料工作台伺服器儲存其狀態檔案的頻率。請參閱[其他配置檔案](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)。

* **Server.cfg：檔** 案會 [!DNL Server.cfg] 指定連接至資料工作台伺服器的資料工作台電腦的預設資料快取大小（以位元組為單位）。請參閱[其他配置檔案](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)。

* **Transform.cfg和Transform Mode.cfg:** 這些檔案只有在您已授權資料轉換功能以搭配您的Adobe應用程式使用時才可用。[!DNL Transform.cfg]檔案包含用於定義日誌源和轉換功能的資料轉換的參數。 您定義的轉換操作源資料，並將其輸出為您指定的格式。 [!DNL Insight Transform Mode.cfg]檔案可讓您暫停資料集中的資料處理、指定離線來源，或指定執行轉換功能的Insight Server儲存其狀態檔案的頻率。 請參閱[轉換功能](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html)。

<!--
c_next_steps.xml
-->

有關特定資料集配置任務的資訊，請使用下表查找並讀取有關您感興趣的任務：

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 如果你想…… </th> 
   <th colname="col2" class="entry"> 另請參閱... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>定義日誌源 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> 記錄來源 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>確定哪些日誌條目在日誌處理期間輸入資料集 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> 資料篩選</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> 記錄項目條件</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>啟用大量事件資料的追蹤ID分割 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> 密鑰拆分</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定Insight Server以檔案伺服器單位的形式執行 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 配置Insight Server檔案伺服器單元  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定Insight Server以集中標準化伺服器的形式執行 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 配置Insight Server檔案伺服器單元  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定用於建立時間維度和進行時間轉換的時區 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> 時區 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>對Adobe提供的內部配置檔案中包含的資料集配置檔案進行小幅更改 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> 編輯現有的資料集包含檔案 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>指定要從記錄處理傳遞至轉換的新資料欄位 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 建立新的資料集包含檔案 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> 記錄處理資料集包含檔案 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>定義轉換 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> 資料轉換 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 建立新的資料集包含檔案 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 轉換資料集包含檔案 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>建立延伸尺寸 </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> 延伸維度 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> 建立新的資料集包含檔案 </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 轉換資料集包含檔案 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>定義要在整個日誌處理或轉換過程中使用的參數 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 定義資料集包含檔案中的參數 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>瞭解可讓您監控或管理資料集的Insight介面 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> 使用資料集組態設定介面 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>隱藏特定延伸維度，使其不會顯示在Insight的維度選單中 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> 隱藏資料集元件 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>覆蓋配置檔案中不能修改或不想修改的某些資料集配置檔案 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> 隱藏資料集元件 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>重新處理您的資料集 </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 重新處理和重新轉換 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>
