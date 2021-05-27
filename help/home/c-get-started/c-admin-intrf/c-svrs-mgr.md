---
description: 系統管理員使用的主要工具是伺服器管理員。
title: 伺服器管理員
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
exl-id: e8b22d9f-3f1b-4a97-942a-85786bd3c547
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---

# 伺服器管理員{#servers-manager}

系統管理員使用的主要工具是伺服器管理員。

它是確定總體系統狀態和執行系統配置、檔案管理和錯誤監視功能的主要介面。

伺服器管理器顯示系統中每個Data Workbench伺服器和[!DNL Sensor]安裝的彩色點（節點），並提供每個安裝的一覽式系統狀態。 也會顯示Data Workbench安裝的節點。

綠色節點表示活動連接，紅色節點表示禁用或無法訪問的連接，灰色節點表示狀態未確定的連接。

![](assets/vis_SysStat_RedGreenDots.png)

按一下右鍵節點可顯示有關連接元件的資訊，並可訪問任何相關菜單。

下表描述了按一下右鍵Data Workbench節點、Data Workbench伺服器(包括群集中的主Data Workbench伺服器)或[!DNL Sensor]時提供的資訊。

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
   <td colname="col2"> <p>產品名稱、版本和組建編號。 </p> <p>範例：Data Workbench5.3(00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>地址 </p> </td> 
   <td colname="col2"> <p>Data Workbench電腦的IP地址。 </p> <p>例如: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定 </p> </td> 
   <td colname="col2"> <p><span class="keyword">Data Workbench</span>配置檔案的連結。 按一下「<span class="uicontrol">設定</span> &gt; <span class="uicontrol"> Insight.cfg </span>」以顯示Data Workbench設定視窗。 您在此視窗中所做和儲存的任何變更，都會反映在Data Workbench安裝目錄的<span class="filepath"> Insight.cfg </span>檔案中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>產品 </p> </td> 
   <td colname="col2"> <p>產品名稱、版本和組建編號。 </p> <p>範例：Data Workbench伺服器5.3(00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Data Workbench伺服器電腦的公用名稱。 </p> <p>範例：<span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>地址 </p> </td> 
   <td colname="col2"> <p>伺服器的IP位址或完全限定的網域名稱，如電腦上的「位址」檔案和<span class="filepath"> Insight.cfg </span>檔案中的「網路位置」參數所設定。 </p> <p>例如: 100.0.0.1 </p> <p>有關地址檔案的資訊，請參閱<i>伺服器產品安裝和管理指南</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>狀態 </p> </td> 
   <td colname="col2"> <p>Data Workbench伺服器的當前狀態。 此欄位在Data Workbench伺服器正常運行時顯示「確定」。 如果發生錯誤，且Data Workbench伺服器節點為紅色，欄位會顯示錯誤（例如「403 Forbidden」）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>詳細狀態 </p> </td> 
   <td colname="col2"> <p><span class="keyword">Data Workbench伺服器</span> <span class="wintitle">詳細狀態</span>介面的連結，對於Data Workbench伺服器的錯誤或其他問題進行故障排除非常有用。 </p> <p>有關詳細資訊，請參閱<a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md">詳細狀態介面</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>遠程案頭 </p> </td> 
   <td colname="col2"> <p>開啟<span class="wintitle">遠程案頭</span>會話至Data Workbench伺服器電腦。 </p> <p>有關詳細資訊，請參閱<a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef">遠程案頭選項</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器檔案 </p> </td> 
   <td colname="col2"> <p>指向<span class="wintitle">伺服器檔案管理器</span>的連結，該連結顯示Data Workbench伺服器安裝目錄中的目錄和檔案。 </p> <p>有關詳細資訊，請參閱<a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4">伺服器檔案管理器</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器監視器 </p> </td> 
   <td colname="col2"> <p>指向<span class="wintitle">伺服器監視器</span>介面的連結，對於故障排除或跟蹤效能參數非常有用。 </p> <p>有關詳細資訊，請參閱<a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45">伺服器監視器介面</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>相關伺服器 </p> </td> 
   <td colname="col2"> <p>僅用於Data Workbench伺服器群集。 </p> <p>列出主<span class="filepath">Data Workbench伺服器的*.address </span>檔案中列出的電腦的公用名稱的菜單。 此清單通常包括群集中的所有處理<span class="keyword">Data Workbench伺服器</span>。 只有當Data Workbench有主<span class="filepath">Data Workbench伺服器的*.address </span>檔案的副本時，才會顯示此菜單。 </p> <p>按一下「<span class="uicontrol">相關伺服器</span>」時，可以按一下以下任一選項： 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> 伺服器監視 </span>器清單，該清單顯 <span class="wintitle"> 示伺服器 </span> 監視器介面，列出所有相關伺服器的詳細資訊 </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">任何Data Workbench伺服器的公用名稱，它顯示上下文菜單，允許您為該特定伺服器開啟以下任一項： 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> 詳細狀 </span>態。請參閱<a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md">詳細狀態介面</a>。 </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> 遠程案 </span>頭。請參閱<a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef">遠程案頭選項</a>。 </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> 伺服器檔案管理員 </span>. 請參閱<a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4">伺服器檔案管理器</a>。 </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> 伺服器監 </span>視器。請參閱<a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45">伺服器監視器介面</a>。 </li> 
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
   <td colname="col2"> <p>產品名稱、版本和組建編號。 </p> <p>範例：Sensor 3.76;J3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> 此安裝的<span class="wintitle">感測器</span>配置檔案中指定的<span class="wintitle">感測器</span> ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>安裝了<span class="wintitle">感測器</span>的Web或應用程式伺服器的IP地址。 </p> <p>例如: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>作業系統指派的處理ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p><span class="wintitle">感測器</span>和Data Workbench伺服器是否使用SSL通信。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>時間 </p> </td> 
   <td colname="col2"> <p>時間 (HH:MM:SS)<span class="wintitle">感測器</span>最後與Data Workbench伺服器建立連接。 </p> </td> 
  </tr> 
 </tbody> 
</table>
