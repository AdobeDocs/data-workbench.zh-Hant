---
description: 「工作台」是您組織及存取所有工作區和報表的位置。
solution: Analytics
title: 工作台
topic: Data workbench
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 工作台{#worktops}

「工作台」是您組織及存取所有工作區和報表的位置。

在大多數情況下，在您 [!DNL Worktop] 開啟「資料工作台」後，會立即顯示。 其功能包括邊 [!DNL Worktop] 欄和標籤式介面。 此外，邊欄可讓您新增視覺化並存取定期使用的函式。

**工作台**

![](assets/client-wktp.png)

您也 [!DNL Worktop] 可以建立和儲存新的和更新的工作區和報表，以及將工作區和報表發佈至資料工作台伺服器，讓其他人存取。

以下 [!DNL Worktop] 的元素表格說明每個元素 [!DNL Worktop]。

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr> 
   <td colname="col1"> 側欄 </td> 
   <td colname="col2"> <p>側欄提供工作區的上下文和控制，以及對工作區當前狀態的感知以及對經常使用功能的訪問。 側欄提供下列功能： </p> <p> <b>連接：</b> 顯示聯機狀態的狀態指示器。 按一下連接狀態以啟用或禁用「在 <span class="wintitle"> 線工作」</span>。 請參 <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> 閱離線和線上工作</a>。 </p> <p> <b>設定檔：</b> 目前使用之描述檔的指標。 </p> <p> <b>截止日期：狀 </b>態指示器，顯示資料在描述檔資料集中的最新狀態。 此資料會從DPU伺服器下載並處理，這只有在您上線時才會發生。 </p> <p> <b>查詢／樣本可信度：</b> 查詢完成的指示符。 當狀態查詢為100%時，已查詢所有資料。 </p> <p> <b>新增：</b> 可讓您將面板、圖例和表格等視覺化新增至側邊欄。 請參 <a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06"> 閱新增視覺化至側欄</a>。 </p> <p> <b>選項：</b> 可讓您回復至先前的側欄設定，並自動隱藏側欄。 </p> <p>當您關閉「資料工作台」 <span class="filepath"> 時，側欄設定會儲存在sidebar</span> .vw檔案中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標籤和子標籤或下拉式子目錄（未顯示） </p> </td> 
   <td colname="col2"> <p>顯示在「工作台」上的每個標籤都對應於「資料工作台」安裝目錄 <span class="wintitle"> 中標籤的「工作設定檔名稱</span> \Workspaces\ <i></i><i></i> 」標籤名稱資料夾，並代表特定類型的資訊，例如控制面板、活動、贏取、訪客等。 Tab name資料夾中的子資料夾預設顯示為子頁籤，但也可以顯示為子目錄。 請參閱 <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> 自訂工作台標籤</a>。 </p> <p> <p>注意： 每個「資料工作台」描述檔都會以標準標籤集傳送。 由於您的實作可以完全自訂，所以顯示的工作區（以及標籤）可能與本指南中的說明不同。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 描述檔狀態 </td> 
   <td colname="col2"> 提供資料工作台伺服器的連線狀態以及目前載入的描述檔名稱。 設定檔資料集中資料的截止日期和時間會顯示線上上指標下方。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小化、最大化、關閉 </td> 
   <td colname="col2"> 標準Windows功能。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 縮圖 </td> 
   <td colname="col2"> <p>縮圖是顯示在「工作台」( <span class="wintitle"> Worktop)上的工作區的快照</span>。 每次保存工作區時都會生成新快照。 縮圖可讓您在「工作台」上快速識別特定工 <span class="wintitle"> 作區</span>。 </p> <p>若要開啟工作區，請按一下縮圖。 </p> <p> <p>注意： 每個「資料工作台」描述檔都會隨一組標準工作區傳送。 由於您的實作可以完全自訂，所以顯示的工作區（以及縮圖）可能與本指南中記載的內容不同。 </p> </p> <p>有關工作區的詳細資訊，請參 <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> 閱配置側欄</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤訊息 </td> 
   <td colname="col2"> <p>錯誤消息以紅色顯示在狀態下。 如需狀態代碼說明，請參 <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> 閱http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>。 </p> <p>例如：403_Forbidden。 </p> </td> 
  </tr> 
 </tbody> 
</table>

