---
description: 將報表入口網站對應至虛擬目錄（IIS 7.0或更新版本）的步驟。
solution: Analytics
title: 將報告門戶映射到虛擬目錄（IIS 7.0或更高版本）
topic: Data workbench
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 將報告門戶映射到虛擬目錄（IIS 7.0或更高版本）{#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

將報表入口網站對應至虛擬目錄（IIS 7.0或更新版本）的步驟。

目前，大多數托管服務客戶端都有帶有Windows Server 2008作業系統和IIS 7.0或更高版本Web伺服器的伺服器。

## 必備條件 {#section-7b1cff24fc4f4c8591540b78de686f2f}

* 請確定IIS 7.0 [!DNL ASP.Net] 或更高版本已安裝ASP和元件。
* 請確定IIS Web用戶具 [!DNL Modify] 有檔案訪 [!DNL E:\Portal\data\users.mdb] 問權。 您可以在檔案上按一下滑鼠右鍵，然 **[!UICONTROL users.mdb]** 後移至標 [!DNL Properties]簽下方來變更 [!DNL Security] 檔案。 如果您未看到列出的IIS Web用戶，或者無法將IIS Web用戶添加到清單中，只需為組提供 [!DNL Users] 訪問 [!DNL Modify] 權。

* 請確定正在運行的任何用戶帳戶 [!DNL Application Pools] 也具有 [!DNL Modify] 對和 [!DNL E:\Portal\data\users.mdb] [!DNL C:\Windows\Temp\]資料夾的訪問權限。

## 安裝步驟 {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. 在安裝的計 [!DNL Report Portal] 算機上，啟動 [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. 選擇 **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. 按一下右鍵並 **[!UICONTROL Default Web Site]** 選擇 **[!UICONTROL Add Virtual Directory]**。

1. 對於別名，請輸入Portal。
1. 對於物理路徑，請輸入 [!DNL E:\Portal\PortalASP]。
1. 按一下 **[!UICONTROL OK]**.

   您建立的虛擬目錄將出現在下 [!DNL Default Web Site]面。

1. 在剛建立的虛擬目錄下添加以下虛擬目錄。

   | 建立此別名…… | 對於此物理資源 |
   |---|---|
   | 核心 | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | 影像 | [!DNL E:\Portal\PortalFiles\Images] |
   | 輸出 | 儲存報表集輸出之目 [!DNL Report Server] 錄的實際位置。 輸出資料夾可位於任何位置，而且可以命名任何內容。 它包含每個報表集的子資料夾。 您可以刪除 [!DNL E:\Portal\PortalFiles\Output]，但將檔案 [!DNL profiles.xml] 移動到輸出檔案的物理位置。 |

1. 完成後，驗證IIS是否顯示四個新的虛擬目錄。 請確定目錄結構有一個父資料夾（與入口資料夾同名）和四個子資料夾。
1. 按一 **[!UICONTROL Application Pools]**&#x200B;下， **[!UICONTROL DefaultAppPool]** 然後（假設您是使用入口網站設定的）。

1. 按一下並 **[!UICONTROL Advanced Settings]** 為「Enable 32-Bit Applications（啟用32位應用程式）」選擇「True（真）」。
1. 為了讓工 [!DNL Portal] 作順利進行，您需要將它轉換為應用程式。 設定虛擬目錄後，按一下右鍵Portal虛擬目錄並選擇 **[!UICONTROL Convert to Application]**。

## 其他秘訣與訣竅 {#section-ff84ab3f66c94620a6a11f0e60471d44}

* 您可從>下 [!DNL Portal] 的Softdocs下載 **[!UICONTROL Softdocs]** 軟體 **[!UICONTROL Report Portal]**。 您只需下載 [!DNL ReportPortal-Release-1-0-0-7.zip]。

* 您不再需要 [!DNL ReportPortalSetup.xml]，因此可以刪除。
* 為了標準化，請將此zip檔的內容放入其中 [!DNL E:\Portal]。
* 要確定SMTP伺服器對於受管理服務客戶端，可在此處查看。
* 請與NetOps一起提出將報表伺服器的IIS中的網域名稱項目變更為更友好的項目的請求，例如 [!DNL reports.clientname.insight.omniture.com]，讓您的整體入口網站URL變更為 [!DNL http://reports.clientname.insight.omniture.com/Portal]。 在完成 [!DNL email.asa] 此變更後，設定您的檔案。

