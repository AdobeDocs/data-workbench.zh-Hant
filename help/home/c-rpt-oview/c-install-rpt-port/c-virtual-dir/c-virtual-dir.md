---
description: 若要設定Report Portal，您必須將其應用程式檔案對應至虛擬目錄。
title: 將 Report Portal 頁面對應至虛擬目錄
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
exl-id: 13e457d4-7039-491a-a65d-f23ad7e9fe77
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 18%

---

# 將 Report Portal 頁面對應至虛擬目錄{#map-the-report-portal-pages-to-virtual-directories}

若要設定Report Portal，您必須將其應用程式檔案對應至虛擬目錄。

虛擬目錄定義了瀏覽器客戶端在IIS應用程式伺服器上查找物理資源時所使用的地址。 要訪問[!DNL Report Portal]，客戶端將其瀏覽器指向您分配給入口的虛擬目錄。

您指派給[!DNL Report Portal]的虛擬目錄名稱必須與上一節步驟3中用於VSVirtualPortalName資料夾的名稱相符。 例如，如果要使用&quot;Portal&quot;作為[!DNL Report Portal]的名稱，必須將入口的檔案映射到名為&quot;Portal&quot;的虛擬目錄。 以下示例顯示客戶端用於訪問在名為myWebServer的伺服器上分配給虛擬目錄[!DNL VisualReportPortal]的[!DNL Report Portal]的URI:

[!DNL https://myWebServer/VisualReportPortal]

以下過程說明如何將[!DNL Report Portal]映射到IIS 5.0、6.0和7.0或更高版本上的虛擬目錄。

請按照您正在使用的IIS版本的一組過程操作：

* [將 Report Portal 對應到虛擬目錄 (IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [將 Report Portal 對應到虛擬目錄 (IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [編輯工作階段組態檔](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)
