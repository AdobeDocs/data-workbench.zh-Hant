---
description: 報表入口網站由一組應用程式伺服器頁面(ASP)和支援檔案組成。
title: 安裝 Report Portal 應用程式檔案
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# 安裝 Report Portal 應用程式檔案{#install-the-report-portal-application-files}

報表入口網站由一組應用程式伺服器頁面(ASP)和支援檔案組成。

要安裝[!DNL Report Portal]，必須從從Adobe收到的分發檔案中解壓這些檔案，然後將它們安裝在運行Microsoft IIS的電腦上。

**安裝應用程 [!DNL Report Portal] 序檔案**

1. 如果您尚未下載[!DNL Report Portal]的安裝套件（.zip檔案），請從AdobeFTP網站下載。
1. 在運行IIS的電腦上，將安裝包中的檔案解壓到任何位置。 此步驟會在VSVirtualPortalName檔案夾中安裝下列子檔案夾和檔案。

   | 資料夾或檔案 | 說明 |
   |---|---|
   | [!DNL \data\users.mdb] | 包含已授權[!DNL Report Portal]用戶清單的資料庫。 |
   | [!DNL \PortalASP\] | 包含組成[!DNL Report Portal]的ASP檔案的資料夾。 |
   | [!DNL \PortalFiles\] | 包含5個子檔案夾（核心、CSS、HTC、影像和輸出），其中包含[!DNL Report Portal]使用的支援檔案。 |
   | [!DNL ReportPortalSetup.xml] | 用於定義與[!DNL Report Portal]關聯的虛擬目錄的配置檔案（僅用於IIS 6.0）。 |

   目錄如下所示：

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >目錄的名稱可能與示例中所示的名稱不同。

1. 將VSVirtualPortalName（或其他名稱）資料夾重新命名為您要用作[!DNL Report Portal]之根虛擬目錄（以下稱為&#x200B;*PortalName*）的資料夾。 有關虛擬目錄的詳細資訊，請參見下一節。
