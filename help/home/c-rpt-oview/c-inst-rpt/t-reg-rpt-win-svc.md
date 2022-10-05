---
description: 註冊和運行報表伺服器的步驟。
title: 將報表伺服器註冊為 Windows 服務
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# 將報表伺服器註冊為 Windows 服務{#registering-report-server-as-a-windows-service}

{{eol}}

註冊和運行報表伺服器的步驟。

在執行此過程之前，請確定 [!DNL Report Server] 服務將運行。 請確定此帳戶擁有存取產生報表儲存位置的適當權限(即，請勿使用 [!DNL Local System Account])。

使用以下過程以開始 [!DNL Report Server]. 開始時 [!DNL Report Server] 它首次自動將自己註冊為Windows服務。

開始時 [!DNL Report Server] 首次會自動連線至Adobe授權伺服器，註冊您的數位憑證。 要成功完成註冊過程，執行以下步驟時，您的電腦必須連接到Internet。

1. 在Windows中，導覽至您安裝的目錄 [!DNL Report Server].

   範例：D:\Adobe\Report

1. 按兩下 **[!UICONTROL ReportServer.exe]**.
1. 確認 [!DNL Report Server] 執行正確，按一下 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. 此命令序列可能因您使用的Windows版本而異。
1. 在服務清單中，找到 [!DNL Report Server] 並確認其狀態為「已啟動」且其啟動類型為「自動」。
1. 執行下列操作以指定其下的用戶帳戶 [!DNL Report Server] 將執行：

   1. 按兩下 **[!UICONTROL Report Server]** 開啟 [!DNL Properties] 窗口。

   1. 選取 **[!UICONTROL Log On]** 標籤。
   1. 選取 **[!UICONTROL This account]** 選項按鈕。
   1. 鍵入或瀏覽帳戶名稱。 此帳戶必須擁有存取儲存產生報表之位置的權限。

      >[!NOTE]
      >
      >若 [!DNL Report Server] 以Microsoft Excel分發報表( [!DNL .xls] 或 [!DNL .xlsx])檔案，請確定帳戶也有執行Microsoft Excel的權限。

   1. 輸入並確認帳戶的密碼。
   1. 按一下 **[!UICONTROL OK]**。

1. 以滑鼠右鍵按一下 [!DNL Report Server] 服務和選擇 **[!UICONTROL Restart]** 以在您指定的帳戶下重新啟動服務。
1. 檢查 [!DNL Report Server] 在啟動期間遇到任何錯誤，請按一下 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. 此命令序列可能因您使用的Windows版本而異。

   1. 在 [!DNL Event Viewer] 窗口，選擇應用程式日誌。
   1. 在右窗格中，尋找Adobe位於 [!DNL Source] 欄。
   1. 如果您從Adobe中發現錯誤，請連按兩下錯誤以顯示 [!DNL Event Properties] 窗口。 此窗口提供有關錯誤的詳細資訊。

      >[!NOTE]
      >
      >在 [!DNL Report Server] 服務啟動，檔案 [!DNL ReportServer.log] 是在報表伺服器中建立 [!DNL Trace] 目錄。 此檔案對於疑難排解 [!DNL Report Server].

您已完成 [!DNL Report Server]. [!DNL Report Server] 設計為持續執行。 如果重新啟動電腦， [!DNL Report Server] 自動重新啟動。 如果您需要開始和停止 [!DNL Report Server] 手動，您可以使用 [!DNL Services] 控制面板。
