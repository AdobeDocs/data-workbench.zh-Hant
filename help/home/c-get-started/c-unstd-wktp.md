---
description: 「工作台」是您組織及存取所有工作區和報表的位置。
title: 操作台
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
exl-id: e714ca25-5e94-408a-9d4e-6e1c13e2a3ef
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# 操作台{#worktops}

「工作台」是您組織及存取所有工作區和報表的位置。

在大多數情況下，[!DNL Worktop]會在您開啟Data Workbench後立即顯示。 [!DNL Worktop]的功能包括邊欄和標籤式介面。 此外，邊欄可讓您新增視覺化並存取定期使用的函式。

**操作台**

![](assets/client-wktp.png)

[!DNL Worktop]還可讓您建立和儲存新的和更新的工作區和報表，以及將工作區和報表發佈至Data Workbench伺服器，讓其他人存取。

下面的[!DNL Worktop]元素表說明了[!DNL Worktop]的每個元素。

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr> 
   <td colname="col1"> 側欄 </td> 
   <td colname="col2"> <p>側欄提供工作區的上下文和控制，以及對工作區當前狀態的感知以及對經常使用功能的訪問。 側欄提供下列功能： </p> <p> <b>連線：顯</b> 示聯機狀態的狀態指示器。按一下連接狀態以啟用或禁用<span class="wintitle">聯機工作</span>。 請參閱<a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54">離線工作和線上</a>。 </p> <p> <b>描述檔：</b> 目前使用中的描述檔指標。 </p> <p> <b>截止日期： </b>狀態指標，顯示資料在描述檔資料集中的最新狀態。此資料會從DPU伺服器下載並處理，這只有在您上線時才會發生。 </p> <p> <b>查詢／抽樣可信度：</b> 查詢完成的指標。當狀態查詢為100%時，已查詢所有資料。 </p> <p> <b>新增：可</b> 讓您將面板、圖例和表格等視覺化新增至側邊欄。請參閱<a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06">新增視覺化至側欄</a>。 </p> <p> <b>選項：</b> 可讓您回復為先前的側邊欄設定，並自動隱藏側邊欄。 </p> <p>當您關閉Data Workbench時，側邊欄設定會儲存在<span class="filepath"> sidebar.vw</span>檔案中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標籤和子標籤或下拉式子目錄（未顯示） </p> </td> 
   <td colname="col2"> <p>顯示在<span class="wintitle"> Worktop</span>上的每個標籤都對應於標籤在Data Workbench安裝目錄中的<i>工作描述檔名稱</i>\Workspaces\<i>tab名稱</i>資料夾，並代表特定類型的資訊，例如控制面板、活動、贏取、訪客等。 Tab name資料夾中的子資料夾預設顯示為子頁籤，但也可以顯示為子目錄。 請參閱<a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc">自訂工作台標籤</a>。 </p> <p> <p>注意： 每個Data Workbench描述檔都會以標準標籤集傳送。 由於您的實作可以完全自訂，所以顯示的工作區（以及標籤）可能與本指南中的說明不同。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 描述檔狀態 </td> 
   <td colname="col2"> 提供與Data Workbench伺服器的連接狀態以及當前載入的配置檔案的名稱。 設定檔資料集中資料的截止日期和時間會顯示線上上指標下方。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小化、最大化、關閉 </td> 
   <td colname="col2"> 標準Windows功能。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 縮圖 </td> 
   <td colname="col2"> <p>縮圖是顯示在<span class="wintitle"> Worktop</span>上的工作區快照。 每次保存工作區時都會生成新快照。 縮圖可讓您在<span class="wintitle"> Worktop</span>中快速識別特定工作區。 </p> <p>若要開啟工作區，請按一下縮圖。 </p> <p> <p>注意： 每個Data Workbench描述檔都會以標準工作區集傳送。 由於您的實作可以完全自訂，所以顯示的工作區（以及縮圖）可能與本指南中記載的內容不同。 </p> </p> <p>有關工作區的詳細資訊，請參閱<a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6">配置側欄</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤訊息 </td> 
   <td colname="col2"> <p>錯誤消息以紅色顯示在狀態下。 如需狀態代碼說明，請參閱<a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>。 </p> <p>例如：403_Forbidden。 </p> </td> 
  </tr> 
 </tbody> 
</table>
