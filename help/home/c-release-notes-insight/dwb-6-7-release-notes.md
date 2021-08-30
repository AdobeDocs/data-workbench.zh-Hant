---
description: Data Workbench6.7的新功能、修正和已知問題。
title: Data Workbench 6.7 發行說明
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
exl-id: e5ec3224-66d1-47a6-9bf3-8be9f6568b8d
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 34%

---

# Data Workbench 6.7 發行說明{#data-workbench-release-notes}

Data Workbench6.7的新功能、修正和已知問題。

## Data Workbench 6.7 發行說明 {#topic-7655534554ac4a4b816af1bd73b06aad}

Data Workbench6.7的新功能、修正和已知問題。

## 第6.7發行版本的新功能 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Data Workbench Workstation 的全新驗證模型 (IMS 整合)**

Data Workbench Workstation 現在支援透過使用者名稱和密碼進行使用者驗證。此用此新方式，管理者即可建立及管理其使用者帳戶，無須與客戶服務聯絡。

如需詳細資訊，請參閱[使用者自我佈建](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html)。

**一般檔案查詢**

Data Workbench Workstation 現在支援透過使用者名稱和密碼進行使用者驗證。此用此新方式，管理者即可建立及管理其使用者帳戶，無須與客戶服務聯絡。

一般檔案查詢功能過去會將整個檔案載入記憶體中緩衝區，使記憶體使用率膨脹，並造成其他子系統出現效能問題。現在，在 Windows 中可將檔案與記憶體對應並建立快取，只要在 ** 中將 Memory Mapped Lookup Files 設定為 [!DNL MemorySettings.cfg]true 即可最佳化記憶體使用率。

如需詳細資訊，請參閱[使用者自我佈建](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html)。

**記憶體使用量**

您現在可以在[!DNL MemorySettings.cfg]中將&#x200B;*使用大型頁面*&#x200B;設為false以停用大型頁面使用。 如需詳細資訊，請參閱[監控記體使用率](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html)。

**安全性加密**

新增 ECDHE 與 DHE 支援。

[!DNL User List.cfg]中的電子郵件支援

在[!DNL User List.cfg]中新增對電子郵件屬性的支援。 如需詳細資訊，請參閱[群組成員的使用者管理](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html?lang=en)。

**說明功能表**

「說明」功能表現在會顯示「開啟憑證」目錄的捷徑。

**`TargetBulkUpload`匯出**

匯出追蹤檔與 `targetbulkuploadexportname.log.completed` 檔的結尾將會提供 URL，以便追蹤停滯批次記錄。

提供新檔案 [!DNL TargetBulkUpload.cfg]，可用於設定「逾時上限」間隔 (以分鐘為單位)。在 [!DNL Server\Admin\Export\]中找到檔案。

## 修正 {#section-160baf6ea04c45a993777ee4260691ed}

* 修正「促銷活動點進」維度顯示膨脹值的問題。
* 修正從報表伺服器產生excel檔案的問題。
* RC4密碼現在預設為禁用。
* 修正在值圖例表格中新增維度元素時，造成Data Workbench工作站當機的問題。
* 修正AAM匯出Data Workbench導致逾時的問題。
* 修正當沒有足夠存取權的使用者將工作區儲存至伺服器時，造成Data Workbench工作站當機的問題。
* 修正[!DNL report.cfg]中的日期格式不正確或未本地化的問題。
* 修正AVRO摘要中的行動和產品列顯示混淆資訊的問題。
* 修正無法在[!DNL order.txt]中排序`*.1cd`和`*.1ad`檔案的問題。

* 在運行群集時，已針對「期望最大化」算法禁用「提交到伺服器」選項。
* 修正了`TargetBulkUpload`執行檔停頓且無法完全執行的問題。

## 已知問題 {#section-d76322bdac5043f087ab303dc68b8fff}

* 登出時，會清除[!DNL user cache.db]檔案。
* 不支援包含「+」或「%」字元的IMS使用者電子郵件地址。
* 在連接狀態錯誤期間，用戶無法註銷。 請以離線模式登出作為因應措施。
* 某些高解析度和高DPI硬體上無法正確呈現IMS登入視窗。 因應措施，請以滑鼠右鍵按一下[!DNL Insight.exe]並導覽至&#x200B;**[!UICONTROL Properties]** > **[!UICONTROL Compatability]**，然後勾選方塊&#x200B;**[!UICONTROL Override high DPI scaling behavior]**。

## 升級需求 {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. 在屬於建置套件一部分的Insight Server上更新[!DNL trust_ca_cert.pem]。
1. 從[https://aap.adobe.com](https://aap.adobe.com)下載新憑證，以更新伺服器和報表伺服器的憑證。
1. 要自動更新工作站和報表伺服器，請從許可證伺服器下載工作站和報表伺服器，手動更新[!DNL trust_ca_cert.pem]。
1. Sensor的自動更新功能需要5.0版才能與Insight Server 6.70版通訊。此外，Sensor的[!DNL trust_ca_cert.pem]必須從授權伺服器下載並手動更新。

## 系統更新 {#section-c1b4949ea734440aa62658ac313261db}

新檔案包括：

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

更新的檔案包括：

1. [!DNL trust_ca_cert.pem] 適用於所有元件。
1. [!DNL Access Control.cfg] 以支援IMS設定。
1. [!DNL Base\Context\meta.cfg] 以支援「開始日期」和「結束日期」格式，在  [!DNL Report.cfg]

1. [!DNL Insight.cfg]新增以支援IMS驗證的Proxy:

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

請參閱[封存的發行說明](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html)，了解Data Workbench5.3到5.52。
