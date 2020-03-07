---
description: 註冊及執行報表伺服器的步驟。
solution: Analytics
title: 將報告伺服器註冊為Windows服務
topic: Data workbench
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 將報告伺服器註冊為Windows服務{#registering-report-server-as-a-windows-service}

註冊及執行報表伺服器的步驟。

在執行此過程之前，請標識服務將運行在其下 [!DNL Report Server] 的Windows帳戶。 請確定此帳戶具有存取所產生報表儲存位置的適當權限(即，請勿使用 [!DNL Local System Account])。

請按下列步驟開始 [!DNL Report Server]。 當您第一次 [!DNL Report Server] 啟動時，它會自動將自己註冊為Windows服務。

當您第一次 [!DNL Report Server] 啟動時，它會自動連線至Adobe License Server，以註冊您的數位憑證。 要成功完成註冊過程，在執行以下步驟時，您的電腦必須連接到Internet。

1. 在Windows中，導覽至您安裝的目錄 [!DNL Report Server]。

   範例：D:\Adobe\Report

1. Double-click **[!UICONTROL ReportServer.exe]**.
1. 若要確認 [!DNL Report Server] 正確執行，請按一下 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**。 此命令序列可能因您使用的Windows版本而異。
1. 在服務清單中，找到條目並確 [!DNL Report Server] 認其狀態為「啟動」，其啟動類型為「自動」。
1. 請執行下列動作，以指定要執行的使 [!DNL Report Server] 用者帳戶：

   1. 按兩下以 **[!UICONTROL Report Server]** 開啟窗 [!DNL Properties] 口。

   1. 選擇選 **[!UICONTROL Log On]** 項卡。
   1. 選擇單 **[!UICONTROL This account]** 選按鈕。
   1. 輸入或瀏覽帳戶名稱。 此帳戶必須擁有存取儲存產生報表之位置的權限。

      >[!NOTE]
      >
      >如果 [!DNL Report Server] 以Microsoft Excel(或 [!DNL .xls][!DNL .xlsx])檔案分發報表，請確定帳戶也擁有執行Microsoft Excel的權限。

   1. 輸入並確認帳戶的密碼。
   1. 按一下 **[!UICONTROL OK]**.

1. 按一下右鍵該服 [!DNL Report Server] 務，並選 **[!UICONTROL Restart]** 擇以指定的帳戶重新啟動服務。
1. 若要檢查啟 [!DNL Report Server] 動期間是否遇到任何錯誤，請按一下 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**。 此命令序列可能因您使用的Windows版本而異。

   1. 在窗口的左窗格中，選 [!DNL Event Viewer] 擇「應用程式」日誌。
   1. 在右窗格中，在欄中尋找Adobe的 [!DNL Source] 事件。
   1. 如果您從Adobe找到錯誤，請按兩下錯誤以顯示視 [!DNL Event Properties] 窗。 此窗口提供了有關錯誤的詳細資訊。

      >[!NOTE]
      >
      >服務啟 [!DNL Report Server] 動後，會在報告 [!DNL ReportServer.log] 伺服器目錄中建立檔 [!DNL Trace] 案。 此檔案也適用於疑難排解問題 [!DNL Report Server]。

您已完成安裝 [!DNL Report Server]。 [!DNL Report Server] 設計為可持續運行。 如果重新啟動電腦，將自動 [!DNL Report Server] 重新啟動。 如果您需要手動啟動和停 [!DNL Report Server] 止，可使用Windows中的控 [!DNL Services] 制面板執行此動作。
