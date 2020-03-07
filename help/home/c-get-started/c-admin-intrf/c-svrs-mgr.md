---
description: 系統管理員使用的主要工具是「伺服器管理器」。
solution: Analytics
title: 伺服器管理員
topic: Data workbench
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# 伺服器管理員{#servers-manager}

系統管理員使用的主要工具是「伺服器管理器」。

它是確定系統整體狀態和執行系統配置、檔案管理和錯誤監控功能的主介面。

「伺服器管理員」會針對系統中的每個資料工作台伺服器和安裝顯示一個彩色點（節點） [!DNL Sensor] ，並提供每個安裝的系統狀態一覽。 它也會顯示資料工作台安裝的節點。

綠色節點表示活動連接，紅色節點表示禁用或無法訪問的連接，灰色節點表示狀態未確定的連接。

![](assets/vis_SysStat_RedGreenDots.png)

按一下右鍵節點可顯示有關連接元件的資訊，並提供對任何相關菜單的訪問。

下表說明在您以滑鼠右鍵按一下「資料工作台」、「資料工作台」伺服器（包括集群中的主資料工作台伺服器）或時所提供的資訊 [!DNL Sensor]。

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>產品 </p> </td> 
   <td colname="col2"> <p>產品名稱、版本和組建編號。 </p> <p>範例：資料工作台5.3(0000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>地址 </p> </td> 
   <td colname="col2"> <p>資料工作台電腦的IP位址。 </p> <p>例如: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定 </p> </td> 
   <td colname="col2"> <p>資料工作台 <span class="keyword"> 組態檔的 </span> 連結。 按一 <span class="uicontrol"> 下「設 </span> 定&gt; <span class="uicontrol"> Insight.cfg」以顯 </span> 示「資料工作台」設定視窗。 您在此視窗中所做的任何變更和儲存，都會反映在資料工作台安 <span class="filepath"> 裝目 </span> 錄的Insight.cfg檔案中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>產品 </p> </td> 
   <td colname="col2"> <p>產品名稱、版本和組建編號。 </p> <p>範例：資料工作台伺服器5.3(0000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>資料工作台伺服器電腦的通用名稱。 </p> <p>範例： <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>地址 </p> </td> 
   <td colname="col2"> <p>伺服器的IP位址或完全限定網域名稱(如電腦上的「位址」檔案和 <span class="filepath"> Insight.cfg檔案中的「網路位置」參數所 </span> 設定)。 </p> <p>例如: 100.0.0.1 </p> <p>有關地址檔案的資訊，請參 <i>閱伺服器產品安裝和管理指南</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>狀態 </p> </td> 
   <td colname="col2"> <p>資料工作台伺服器的目前狀態。 當資料工作台伺服器正常執行時，此欄位會顯示「確定」。 如果發生錯誤，而「資料工作台」伺服器節點為紅色，則欄位會顯示錯誤（例如「403 Forbidden」）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>詳細狀態 </p> </td> 
   <td colname="col2"> <p>連結至「資料工作台 <span class="keyword"> 伺服器詳細 </span> 狀態」介面， <span class="wintitle"></span> 這對於疑難排解「資料工作台」伺服器的錯誤或其他問題非常有用。 </p> <p>如需詳細資訊，請參 <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> 閱詳細狀態介面</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>遠程案頭 </p> </td> 
   <td colname="col2"> <p>開啟與數 <span class="wintitle"> 據工作台服 </span> 務器電腦的遠程案頭會話。 </p> <p>有關詳細資訊，請參 <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> 閱遠程案頭選項 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器檔案 </p> </td> 
   <td colname="col2"> <p>「伺服器檔案管 <span class="wintitle"> 理器」的連結， </span>會在「資料工作台」伺服器安裝目錄中顯示目錄和檔案。 </p> <p>如需詳細資訊，請參 <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> 閱伺服器檔案管理 </a>器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器監視程式 </p> </td> 
   <td colname="col2"> <p>伺服器監視程 <span class="wintitle"> 式介面的連 </span> 結，對疑難排解或追蹤效能參數非常有用。 </p> <p>如需詳細資訊，請參 <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> 閱伺服器監視器介面 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>相關伺服器 </p> </td> 
   <td colname="col2"> <p>僅適用於資料工作台伺服器叢集。 </p> <p>列出主資料工作台伺服器*.address檔案中所列之電 <span class="filepath"> 腦之通用名稱的功 </span> 能表。 此清單通常包含叢集中所有處 <span class="keyword"> 理資料工作台 </span> 伺服器。 此功能表僅會在「資料工作台」有主資料工作台伺服器*.address檔 <span class="filepath"> 案的副本時 </span> 顯示。 </p> <p>按一下「相 <span class="uicontrol"> 關伺服器」 </span>後，您可以按一下下列任一項： 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> 伺服器監 </span>視器清單，其中顯示 <span class="wintitle"> 伺服器監 </span> 視器介面列出所有相關伺服器的詳細資訊 </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">任何資料工作台伺服器的公用名稱，此伺服器會顯示內容功能表，讓您針對該特定伺服器開啟下列任一項： 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> 詳細狀態 </span>。 請參 <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> 閱詳細的狀態介 </a>面。 </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> 遠程案頭 </span>。 請參 <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> 閱遠程案頭選項 </a>。 </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> 伺服器檔案管 </span>理器。 請參 <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> 閱伺服器檔案管理 </a>器。 </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> 伺服器監 </span>視器。 請參 <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> 閱伺服器監視器介 </a>面。 </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_5BFA0AFE2D9A4337BF04343879DAD03B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>產品 </p> </td> 
   <td colname="col2"> <p>產品名稱、版本和組建編號。 </p> <p>範例：感測器3.76;J3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> 在此安 <span class="wintitle"> 裝的感測器配置文 </span> 件中指 <span class="wintitle"></span> 定的感測器ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>安裝感測器的Web或應用程式伺服器 <span class="wintitle"> 的IP </span> 地址。 </p> <p>例如: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>作業系統指派的流程ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>感測器 <span class="wintitle"> 與數 </span> 據工作台伺服器是否使用SSL進行通信。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>時間 </p> </td> 
   <td colname="col2"> <p>時間 (HH:MM:SS)，感測器上 <span class="wintitle"> 次 </span> 與資料工作台伺服器建立連接。 </p> </td> 
  </tr> 
 </tbody> 
</table>
