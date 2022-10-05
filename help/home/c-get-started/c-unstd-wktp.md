---
description: 操作台是您組織及存取所有工作區和報表的位置。
title: 操作台
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
exl-id: e714ca25-5e94-408a-9d4e-6e1c13e2a3ef
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# 操作台{#worktops}

{{eol}}

操作台是您組織及存取所有工作區和報表的位置。

在大多數情況下， [!DNL Worktop] 會在您開啟Data Workbench後立即顯示。 的功能 [!DNL Worktop] 包括側欄和標籤式介面。 此外，側欄可讓您新增視覺效果並存取經常使用的函式。

**操作台**

![](assets/client-wktp.png)

此 [!DNL Worktop] 也可讓您建立和儲存新的和更新的工作區與報表，以及將工作區與報表發佈至Data Workbench伺服器，供其他人存取。

此 [!DNL Worktop] 下表的元素說明了 [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689">
 <tbody>
  <tr>
   <td colname="col1"> 側欄 </td>
   <td colname="col2"> <p>側欄提供工作區的上下文和控制，以及對工作區當前狀態和對經常使用功能的訪問的感知。 側欄提供下列函式： </p> <p> <b>連接：</b> 顯示聯機狀態的狀態指示器。 按一下連接狀態以啟用或禁用 <span class="wintitle"> 線上工作</span>. 請參閱 <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> 離線和線上工作</a>. </p> <p> <b>設定檔：</b> 目前使用中設定檔的指標。 </p> <p> <b>截止日期： </b>狀態指標，顯示設定檔資料集中資料的最新狀態。 此資料會從DPU伺服器下載並處理，而這只有在您上線時才會發生。 </p> <p> <b>查詢/樣本可信度：</b> 查詢完成的指標。 當狀態查詢為100%時，已查詢所有資料。 </p> <p> <b>添加：</b> 可讓您將面板、圖例和表格等視覺效果新增至側邊欄。 請參閱 <a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06"> 新增視覺效果至側欄</a>. </p> <p> <b>選項：</b> 可讓您回復到先前的側欄設定，並自動隱藏側欄。 </p> <p>側邊欄設定儲存在 <span class="filepath"> sidebar.vw</span> 檔案時填入Data Workbench。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>標籤和子標籤或下拉式子目錄（未顯示） </p> </td>
   <td colname="col2"> <p>顯示在 <span class="wintitle"> 操作台</span> 與索引標籤的 <i>工作設定檔名稱</i>\工作區\<i>標籤名稱</i> 資料夾，並代表特定類型的資訊，例如控制面板、活動、贏取、訪客等。 索引標籤名稱資料夾中的子資料夾預設會顯示為子索引標籤，但也可顯示為子目錄。 請參閱 <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> 自訂操作台標籤</a>. </p> <p> <p>注意：每個Data Workbench設定檔都會隨標準標籤集傳送。 由於您的實作可以完全自訂，所以顯示的工作區（以及因此，索引標籤）可能與本指南中說明的不同。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 設定檔狀態 </td>
   <td colname="col2"> 提供與Data Workbench伺服器的連線狀態以及目前載入之設定檔的名稱。 設定檔資料集中資料的「截止日期」日期和時間會顯示線上上指標下方。 </td>
  </tr>
  <tr>
   <td colname="col1"> 最小化，最大化，關閉 </td>
   <td colname="col2"> 標準Windows功能。 </td>
  </tr>
  <tr>
   <td colname="col1"> 縮圖 </td>
   <td colname="col2"> <p>縮圖是顯示在 <span class="wintitle"> 操作台</span>. 每次保存工作區時都會建立新快照。 縮圖可讓您快速識別 <span class="wintitle"> 操作台</span>. </p> <p>若要開啟工作區，請按一下縮圖。 </p> <p> <p>注意：每個Data Workbench設定檔都會與標準工作區集一併傳送。 由於您的實作可以完全自訂，所以顯示的工作區（以及縮圖）可能與本指南中記錄的不同。 </p> </p> <p>如需工作區的詳細資訊，請參閱 <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> 配置側欄</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 錯誤訊息 </td>
   <td colname="col2"> <p>錯誤訊息會在狀態下方以紅色顯示。 如需狀態代碼說明，請參閱 <a href="https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>例如：403_禁止。 </p> </td>
  </tr>
 </tbody>
</table>
