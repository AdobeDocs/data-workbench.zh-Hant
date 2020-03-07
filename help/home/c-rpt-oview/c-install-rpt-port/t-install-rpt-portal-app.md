---
description: 報表入口網站由一組應用程式伺服器頁面(ASP)和支援檔案組成。
solution: Analytics
title: 安裝報告入口應用程式檔案
topic: Data workbench
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安裝報告入口應用程式檔案{#install-the-report-portal-application-files}

報表入口網站由一組應用程式伺服器頁面(ASP)和支援檔案組成。

若要安裝 [!DNL Report Portal]，您必須從您從Adobe收到的散發檔案中擷取這些檔案，並將它們安裝在執行Microsoft IIS的機器上。

**安裝應用程[!DNL Report Portal]序檔案**

1. 如果您尚未這麼做，請從Adobe FTP網站下載適用於 [!DNL Report Portal] 的安裝套件（.zip檔案）。
1. 在運行IIS的電腦上，將安裝包中的檔案解壓到任何位置。 此步驟會在VSVirtualPortalName檔案夾中安裝下列子檔案夾和檔案。

   | 資料夾或檔案 | 說明 |
   |---|---|
   | [!DNL \data\users.mdb] | 包含授權用戶清單的數 [!DNL Report Portal] 據庫。 |
   | [!DNL \PortalASP\] | 包含組成的ASP檔案的資料夾 [!DNL Report Portal]。 |
   | [!DNL \PortalFiles\] | 包含5個子檔案夾（核心、CSS、HTC、影像和輸出），其中包含支援檔案的檔案夾 [!DNL Report Portal]。 |
   | [!DNL ReportPortalSetup.xml] | 用於定義與關聯的虛擬目錄的配 [!DNL Report Portal] 置檔案（僅用於IIS 6.0）。 |

   目錄如下所示：

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >目錄的名稱可能與示例中所示的名稱不同。

1. 將VSVirtualPortalName（或其他名稱）資料夾重新命名為您要用作根虛擬目錄的 [!DNL Report Portal] 資料夾(以下稱 *為PortalName*)。 有關虛擬目錄的詳細資訊，請參見下一節。
