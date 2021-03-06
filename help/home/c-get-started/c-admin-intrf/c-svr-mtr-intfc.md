---
description: 「伺服器監視器」介面對於故障排除或僅跟蹤Data Workbench伺服器電腦的效能參數非常有用，並報告作為Data Workbench伺服器電腦客戶端的電腦。
title: 伺服器監視器介面
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# 伺服器監視器介面{#server-monitor-interface}

「伺服器監視器」介面對於故障排除或僅跟蹤Data Workbench伺服器電腦的效能參數非常有用，並報告作為Data Workbench伺服器電腦客戶端的電腦。

伺服器監視器介面在電腦名稱的左側的頂部顯示綠色點或紅點。 綠色圓點表示電腦正常工作，無問題。 紅點表示電腦上發生了一個或多個錯誤。

伺服器監視器介面的下部列出每個可用配置檔案的處理狀態以及有關電腦的效能詳細資訊。

有關[!DNL Data Workbench servers]的詳細資訊，請參閱&#x200B;*伺服器產品安裝和管理指南*。 如需[!DNL Report]的詳細資訊，請參閱&#x200B;*Data Workbench報表指南*。

**要開啟「伺服器監視器」介面，請執行以下操作**

* 在「伺服器管理器」中，按一下右鍵Data Workbench伺服器或[!DNL Report]電腦的節點。 t

按一下&#x200B;**[!UICONTROL Server Monitor]**&#x200B;查看有關一台伺服器的詳細資訊，或按一下&#x200B;**[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]**&#x200B;查看有關伺服器群集的詳細資訊。

![](assets/vis_ServerMonitor.png)

[!DNL Server Monitor]介面每10秒自動更新一次。

下表列出了可使用[!DNL Server Monitor]介面完成的任務。

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要執行此任務…… </th> 
   <th colname="col2" class="entry"> 執行動作... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>檢查設定檔的記錄處理狀態 </p> </td> 
   <td colname="col2"> <p>查看配置檔案<i>配置檔案</i>名稱向量。 在上例中，您可以查看Profile ExampleProfile向量，以查看ExampleProfile配置檔案在一台伺服器上的進程，其日誌處理完成100%。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>確定電腦響應請求所需的時間 </p> </td> 
   <td colname="col2"> <p>查看輪詢延遲欄位。 如果此值大於1000ms，請聯絡Adobe支援服務。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看完成轉換或查詢可能需要多久的估計值 </p> </td> 
   <td colname="col2"> <p>查看僅在轉換或查詢期間顯示的掃描時間(hh:mm:ss)欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>確定與電腦的當前網路連接數 </p> </td> 
   <td colname="col2"> <p>查看電腦的<span class="wintitle">伺服器監視器</span>資訊的最後一行。 在上例中，您看到當前有2個網路連接來自一台電腦。 </p> </td> 
  </tr> 
 </tbody> 
</table>
