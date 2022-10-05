---
description: 將Report Portal對應到虛擬目錄（IIS 7.0或更新版本）的步驟。
title: 將 Report Portal 對應到虛擬目錄 (IIS 7.0 或更新版本)
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 5%

---

# 將 Report Portal 對應到虛擬目錄 (IIS 7.0 或更新版本){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

{{eol}}

將Report Portal對應到虛擬目錄（IIS 7.0或更新版本）的步驟。

目前，大多數托管服務客戶端都具有帶有Windows Server 2008作業系統和IIS 7.0或更高版本Web伺服器的伺服器。

## 先決條件 {#section-7b1cff24fc4f4c8591540b78de686f2f}

* 確保ASP和 [!DNL ASP.Net] 為IIS 7.0或更高版本安裝元件。
* 確保IIS Web用戶已 [!DNL Modify] 存取 [!DNL E:\Portal\data\users.mdb] 檔案。 您可以按一下滑鼠右鍵， **[!UICONTROL users.mdb]** 檔案和下 [!DNL Properties]，前往 [!DNL Security] 標籤。 如果未列出IIS Web用戶，或者無法將IIS Web用戶添加到清單中，只需將 [!DNL Users] 群組 [!DNL Modify] 存取權。

* 請確定使用任何使用者帳戶來執行 [!DNL Application Pools] 也有 [!DNL Modify] 存取 [!DNL E:\Portal\data\users.mdb] 和[!DNL C:\Windows\Temp\]資料夾。

## 安裝步驟 {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. 在 [!DNL Report Portal] 已安裝，請啟動 [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. 選擇 **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. 按一下右鍵 **[!UICONTROL Default Web Site]** 選取 **[!UICONTROL Add Virtual Directory]**.

1. 對於別名，請輸入Portal。
1. 對於物理路徑，請輸入 [!DNL E:\Portal\PortalASP].
1. 按一下 **[!UICONTROL OK]**。

   您建立的虛擬目錄會顯示在 [!DNL Default Web Site].

1. 在您剛建立的虛擬目錄下新增下列虛擬目錄。

   | 建立此別名…… | 對於此物理資源 |
   |---|---|
   | 核心 | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | 影像 | [!DNL E:\Portal\PortalFiles\Images] |
   | 輸出 | 目錄的物理位置，其中 [!DNL Report Server] 儲存報表集的輸出。 輸出資料夾可位於任意位置，可命名為任何內容。 它包含每個報表集的子資料夾。 您可以刪除 [!DNL E:\Portal\PortalFiles\Output]，但移動 [!DNL profiles.xml] 到輸出檔案的物理位置。 |

1. 完成後，驗證IIS是否顯示四個新的虛擬目錄。 請確保目錄結構有一個父資料夾（與門戶名稱相同）和四個子資料夾。
1. 按一下 **[!UICONTROL Application Pools]**，然後 **[!UICONTROL DefaultAppPool]** （假設這是您用入口網站設定的那個）。

1. 按一下 **[!UICONTROL Advanced Settings]** 並為「啟用32位應用程式」選擇「True」。
1. 若要取得 [!DNL Portal] 若要運作，您需要將其轉換為應用程式。 設定虛擬目錄後，按一下右鍵Portal虛擬目錄，然後選擇 **[!UICONTROL Convert to Application]**.

## 其他提示與秘訣 {#section-ff84ab3f66c94620a6a11f0e60471d44}

* 您可以下載 [!DNL Portal] 從下方的Softdocs **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. 您只需下載 [!DNL ReportPortal-Release-1-0-0-7.zip].

* 您不再需要 [!DNL ReportPortalSetup.xml]，以便刪除。
* 為了標準化，請將此zip檔案的內容放入 [!DNL E:\Portal].
* 要確定SMTP伺服器對於托管服務客戶端，可以查看這裡。
* 請使用NetOps將報表伺服器的IIS中的網域名稱項目變更為更好記的項目，例如 [!DNL reports.clientname.insight.omniture.com]，以便您的整體入口URL為 [!DNL https://reports.clientname.insight.omniture.com/Portal]. 設定您的 [!DNL email.asa] 檔案。
