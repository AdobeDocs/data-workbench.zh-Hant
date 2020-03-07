---
description: 若要設定報表入口網站，您必須將其應用程式檔案對應至虛擬目錄。
solution: Analytics
title: 將報表入口網頁映射至虛擬目錄
topic: Data workbench
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 將報表入口網頁映射至虛擬目錄{#map-the-report-portal-pages-to-virtual-directories}

若要設定報表入口網站，您必須將其應用程式檔案對應至虛擬目錄。

虛擬目錄定義了瀏覽器客戶端在IIS應用程式伺服器上查找物理資源時使用的地址。 若要存 [!DNL Report Portal]取，用戶端會將其瀏覽器指向您指派給入口網站的虛擬目錄。

您指派給的虛擬目錄名稱必 [!DNL Report Portal] 須與您在上一節步驟3中用於VSVirtualPortalName資料夾的名稱相符。 例如，如果您想使用「Portal」做為您的名稱 [!DNL Report Portal]，則必須將入口網站的檔案對應至名為「Portal」的虛擬目錄。以下示例顯示客戶端用於訪問在名為myWebServer的服 [!DNL Report Portal] 務器上分配給虛擬目 [!DNL VisualReportPortal] 錄的URI:

[!DNL http://myWebServer/VisualReportPortal]

以下過程介紹如 [!DNL Report Portal] 何映射到IIS 5.0、6.0和7.0或更高版本上的虛擬目錄。

按照您正在使用的IIS版本的一組過程進行操作：

* [將報告門戶映射到虛擬目錄(IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [將報告門戶映射到虛擬目錄(IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \編 [輯會話配置檔案](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)

