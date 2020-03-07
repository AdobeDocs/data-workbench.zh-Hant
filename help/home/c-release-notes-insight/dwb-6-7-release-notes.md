---
description: 資料工作台6.7的新功能、修正和已知問題。
title: 資料工作台6.7發行說明
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.7 Release Notes{#data-workbench-release-notes}

資料工作台6.7的新功能、修正和已知問題。

## Data Workbench 6.7 Release Notes {#topic-7655534554ac4a4b816af1bd73b06aad}

資料工作台6.7的新功能、修正和已知問題。

## 6.7版中的新功能 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Data Workbench Workstation 的全新驗證模型 (IMS 整合)**

Data Workbench Workstation 現在支援透過使用者名稱和密碼進行使用者驗證。此用此新方式，管理者即可建立及管理其使用者帳戶，無須與客戶服務聯絡。

如需詳細資訊，請參閱[使用者自我佈建](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html)。

**一般檔案查詢**

Data Workbench Workstation 現在支援透過使用者名稱和密碼進行使用者驗證。此用此新方式，管理者即可建立及管理其使用者帳戶，無須與客戶服務聯絡。

一般檔案查詢功能過去會將整個檔案載入記憶體中緩衝區，使記憶體使用率膨脹，並造成其他子系統出現效能問題。現在，在 Windows 中可將檔案與記憶體對應並建立快取，只要在 *中將* Memory Mapped Lookup Files[!DNL MemorySettings.cfg] 設定為 true 即可最佳化記憶體使用率。

如需詳細資訊，請參閱[使用者自我佈建](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html)。

**記憶體使用**

Large Page usage can now be disabled by setting *Use Large Pages* to false in [!DNL MemorySettings.cfg]. 如需詳細資訊，請參閱[監控記體使用率](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html)。

**安全性加密**

新增 ECDHE 與 DHE 支援。

Email support in [!DNL User List.cfg]

Added support for Email attribute in [!DNL User List.cfg]. 如需詳細資訊，請參閱[群組成員的使用者管理](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html)。

**說明功能表**

「說明」功能表現在會顯示「開啟憑證」目錄的捷徑。

**`TargetBulkUpload`匯出&#x200B;**

匯出追蹤檔與 `targetbulkuploadexportname.log.completed` 檔的結尾將會提供 URL，以便追蹤停滯批次記錄。

提供新檔案 [!DNL TargetBulkUpload.cfg]，可用於設定「逾時上限」間隔 (以分鐘為單位)。檔案位於[!DNL Server\Admin\Export\]中。

## 修正 {#section-160baf6ea04c45a993777ee4260691ed}

* 修正「促銷活動點進」維度顯示誇大值的問題。
* 修正從報表伺服器產生Excel檔案的問題。
* RC4密碼現在預設禁用。
* 修正在值圖例表格中新增維度元素時，造成「資料工作台」工作站當機的問題。
* 修正造成逾時的AAM匯出資料工作台問題。
* 修正當使用者沒有足夠的存取權限，將工作區儲存至伺服器時，造成資料工作台工作站當機的問題。
* 修正日期格式不正確或未 [!DNL report.cfg] 本地化的問題。
* 修正AVRO饋送中行動與產品列顯示混淆資訊的問題。
* 修正無法排序和檔案 `*.1cd` 的 `*.1ad` 問題 [!DNL order.txt]。

* 在運行聚類時，對於期望最大化算法，「提交到伺服器」選項已被禁用。
* 已修正執行檔 `TargetBulkUpload` 停滯且無法完全執行的問題。

## 已知問題 {#section-d76322bdac5043f087ab303dc68b8fff}

* 登出時，會清 [!DNL user cache.db] 理檔案。
* 不支援包含&#39;+&#39;或&#39;%&#39;字元的IMS使用者電子郵件地址。
* 在連接狀態出錯期間，用戶無法註銷。 因應措施，請在離線模式下登出。
* IMS登入視窗無法在高解析度和高DPI的硬體上正確顯示。 因應措施，請以滑鼠右鍵按一 [!DNL Insight.exe] 下並導覽至 **[!UICONTROL Properties]** > **[!UICONTROL Compatability]**，然後核取方塊 **[!UICONTROL Override high DPI scaling behavior]**。

## 升級需求 {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. 在作 [!DNL trust_ca_cert.pem] 為建置套件一部分的Insight Server上更新。
1. 從https://aap.adobe.com下載新憑證，以更新伺服器和報表伺服器的 [憑證](https://aap.adobe.com)。
1. 要自動更新工作站和報告伺服器，請從許 [!DNL trust_ca_cert.pem] 可證伺服器下載工作站和報告伺服器，手動更新。
1. 感測器的自動更新功能需要5.0版才能與Insight Server 6.70版通訊。此外，感測器必 [!DNL trust_ca_cert.pem] 須通過從許可證伺服器下載來手動更新。

## 系統更新 {#section-c1b4949ea734440aa62658ac313261db}

新檔案包括：

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

更新的檔案包括：

1. [!DNL trust_ca_cert.pem] 所有元件。
1. [!DNL Access Control.cfg] 以支援IMS設定。
1. [!DNL Base\Context\meta.cfg] 以支援「開始日期」和「結束日期」格式， [!DNL Report.cfg]

1. 支援IMS [!DNL Insight.cfg] 驗證之Proxy的新增功能：

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

請參 [閱「資料工作台](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) 5.3至5.52的封存發行說明」。
