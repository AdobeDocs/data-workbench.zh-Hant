---
description: 將報表入口網站對應至虛擬目錄（IIS 7.0或更新版本）的步驟。
title: 將 Report Portal 對應到虛擬目錄 (IIS 7.0 或更新版本)
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---

# 將 Report Portal 對應到虛擬目錄 (IIS 7.0 或更新版本){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

將報表入口網站對應至虛擬目錄（IIS 7.0或更新版本）的步驟。

目前，大多數托管服務客戶端都有帶有Windows Server 2008作業系統和IIS 7.0或更高版本Web伺服器的伺服器。

## 必備條件 {#section-7b1cff24fc4f4c8591540b78de686f2f}

* 請確定IIS 7.0或更高版本已安裝ASP和[!DNL ASP.Net]元件。
* 確保IIS Web用戶具有[!DNL Modify]對[!DNL E:\Portal\data\users.mdb]檔案的訪問權。 您可以在&#x200B;**[!UICONTROL users.mdb]**&#x200B;檔案上按一下滑鼠右鍵，然後在[!DNL Properties]下方移至[!DNL Security]標籤。 如果您未看到列出的IIS Web用戶，或者無法將IIS Web用戶添加到清單中，只需為[!DNL Users]組提供[!DNL Modify]訪問權限。

* 請確定使用任何用戶帳戶來運行[!DNL Application Pools]還具有對[!DNL E:\Portal\data\users.mdb]和 [!DNL C:\Windows\Temp\] 資料夾的[!DNL Modify]訪問權限。

## 安裝步驟{#section-2a6476a221fa43dfa91866c0d41f82e5}

1. 在安裝[!DNL Report Portal]的電腦上，啟動[!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. 選擇 **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. 按一下右鍵&#x200B;**[!UICONTROL Default Web Site]**&#x200B;並選擇&#x200B;**[!UICONTROL Add Virtual Directory]**。

1. 對於別名，請輸入Portal。
1. 對於物理路徑，輸入[!DNL E:\Portal\PortalASP]。
1. 按一下 **[!UICONTROL OK]**。

   您建立的虛擬目錄將出現在[!DNL Default Web Site]下。

1. 在剛建立的虛擬目錄下添加以下虛擬目錄。

   | 建立此別名…… | 對於此物理資源 |
   |---|---|
   | Core | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | 影像 | [!DNL E:\Portal\PortalFiles\Images] |
   | 輸出 | [!DNL Report Server]儲存報表集輸出之目錄的物理位置。 輸出資料夾可位於任何位置，而且可以命名任何內容。 它包含每個報表集的子資料夾。 您可以刪除[!DNL E:\Portal\PortalFiles\Output]，但將[!DNL profiles.xml]移至輸出檔案的物理位置。 |

1. 完成後，驗證IIS是否顯示四個新的虛擬目錄。 請確定目錄結構有一個父資料夾（與入口資料夾同名）和四個子資料夾。
1. 按一下&#x200B;**[!UICONTROL Application Pools]**，然後按一下&#x200B;**[!UICONTROL DefaultAppPool]**（假設您是使用入口網站設定的）。

1. 按一下&#x200B;**[!UICONTROL Advanced Settings]**&#x200B;並為「Enable 32-Bit Applications（啟用32位應用程式）」選擇「True（真）」。
1. 若要讓[!DNL Portal]運作，您必須將它轉換為應用程式。 設定虛擬目錄後，按一下右鍵Portal虛擬目錄並選擇&#x200B;**[!UICONTROL Convert to Application]**。

## 其他提示與秘訣{#section-ff84ab3f66c94620a6a11f0e60471d44}

* 您可從Softdocs下載&#x200B;**[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**&#x200B;下的[!DNL Portal]。 您只需下載[!DNL ReportPortal-Release-1-0-0-7.zip]。

* 您不再需要[!DNL ReportPortalSetup.xml]，因此可以刪除它。
* 為了標準化，請將此zip檔案的內容放入[!DNL E:\Portal]。
* 要確定SMTP伺服器對於受管理服務客戶端，可在此處查看。
* 請求NetOps將報表伺服器的IIS中的網域名稱項目變更為更友好的項目——例如[!DNL reports.clientname.insight.omniture.com]，讓您的整體入口網站URL為[!DNL http://reports.clientname.insight.omniture.com/Portal]。 在此變更生效後，設定您的[!DNL email.asa]檔案。
