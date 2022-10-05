---
description: Report Portal由一組應用程式伺服器頁面(ASP)和支援檔案組成。
title: 安裝 Report Portal 應用程式檔案
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# 安裝 Report Portal 應用程式檔案{#install-the-report-portal-application-files}

{{eol}}

Report Portal由一組應用程式伺服器頁面(ASP)和支援檔案組成。

若要安裝 [!DNL Report Portal]，您必須從從Adobe收到的發佈檔案中擷取這些檔案，並安裝在執行Microsoft IIS的電腦上。

**安裝 [!DNL Report Portal] 應用程式檔案**

1. 若尚未這麼做，請下載 [!DNL Report Portal] 從AdobeFTP站台。
1. 在運行IIS的電腦上，將安裝包中的檔案解壓到任何位置。 此步驟會在VSVirtualPortalName資料夾中安裝下列子資料夾和檔案。

   | 資料夾或檔案 | 說明 |
   |---|---|
   | [!DNL \data\users.mdb] | 包含授權清單的資料庫 [!DNL Report Portal] 使用者。 |
   | [!DNL \PortalASP\] | 包含ASP檔案的資料夾，這些檔案組成 [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | 包含5個子資料夾（核心、CSS、HTC、影像和輸出）的資料夾，這些子資料夾包含 [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | 用於定義與關聯的虛擬目錄的配置檔案 [!DNL Report Portal] （僅與IIS 6.0一起使用）。 |

   目錄如下列範例所示：

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >目錄的名稱可能與示例中所示的名稱不同。

1. 將VSVirtualPortalName（或其他名稱）資料夾重新命名為您要用作您的 [!DNL Report Portal] (下稱 *PortalName*)。 有關虛擬目錄的詳細資訊，請參見下一節。
