---
description: 伺服器監視程式介面對於疑難排解或僅追蹤資料工作台伺服器電腦和報告伺服器電腦（為資料工作台伺服器電腦的用戶端）的效能參數十分有用。
solution: Analytics
title: 伺服器監視器介面
topic: Data workbench
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 伺服器監視器介面{#server-monitor-interface}

伺服器監視程式介面對於疑難排解或僅追蹤資料工作台伺服器電腦和報告伺服器電腦（為資料工作台伺服器電腦的用戶端）的效能參數十分有用。

「Server Monitor（伺服器監視器）」介面在電腦名稱的左側顯示一個綠色點或一個紅色點。 綠點表示電腦正常工作，無問題。 紅點表示電腦上發生了一個或多個錯誤。

伺服器監視器介面的下部列出了每個可用配置檔案的處理狀態以及電腦的效能詳細資訊。

如需詳細資訊 [!DNL Data Workbench servers]，請參 *閱伺服器產品安裝與管理指南*。 如需詳細資訊，請 [!DNL Report]參閱「資 *料工作台報表指南」*。

**要開啟伺服器監視器介面**

* 在「伺服器管理員」中，以滑鼠右鍵按一下「資料工作台」伺服器或電腦的 [!DNL Report] 節點。 t

按一下 **[!UICONTROL Server Monitor]** 查看有關一台伺服器的詳細資訊，或按一下 **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** 查看有關相關伺服器集群的詳細資訊。

![](assets/vis_ServerMonitor.png)

介面 [!DNL Server Monitor]每10秒自動更新一次。

下表列出了可使用介面完成的 [!DNL Server Monitor] 任務。

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要執行此任務…… </th> 
   <th colname="col2" class="entry"> 執行動作... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>要檢查配置檔案的日誌處理狀態 </p> </td> 
   <td colname="col2"> <p>檢視描述檔 <i>名稱</i> 向量。 在上述範例中，您會檢視Profile ExampleProfile向量，以查看ExampleProfile描述檔會在一個伺服器上處理，其記錄檔處理完成100%。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>確定電腦響應請求所需的時間 </p> </td> 
   <td colname="col2"> <p>檢視民調問答延遲欄位。 如果此值大於1000ms，請聯絡Adobe支援服務。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要查看完成轉換或查詢所需時間的估計值 </p> </td> 
   <td colname="col2"> <p>查看僅在轉換或查詢期間顯示的掃描時間(hh:mm:ss)欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>確定與電腦的當前網路連接數 </p> </td> 
   <td colname="col2"> <p>檢視電腦的「伺服器監視程式」 <span class="wintitle"> 資訊的最後一行</span> 。 在上述範例中，您看到目前有2個網路連線來自一部電腦。 </p> </td> 
  </tr> 
 </tbody> 
</table>

