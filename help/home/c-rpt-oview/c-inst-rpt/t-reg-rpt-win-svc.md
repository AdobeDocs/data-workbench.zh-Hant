---
description: 註冊和運行報表伺服器的步驟。
title: 將報表伺服器註冊為 Windows 服務
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# 將報表伺服器註冊為 Windows 服務{#registering-report-server-as-a-windows-service}

註冊和運行報表伺服器的步驟。

在執行此過程之前，請確定[!DNL Report Server]服務將在其下運行的Windows帳戶。 請確定此帳戶具有存取所產生報表儲存位置的適當權限（即，請勿使用[!DNL Local System Account]）。

使用以下過程啟動[!DNL Report Server]。 當您首次啟動[!DNL Report Server]時，它會自動將自己註冊為Windows服務。

當您首次啟動[!DNL Report Server]時，它會自動連接到Adobe許可證伺服器以註冊您的數字證書。 要成功完成註冊過程，執行以下步驟時，您的電腦必須連接到Internet。

1. 在Windows中，導航至安裝[!DNL Report Server]的目錄。

   範例：D:\Adobe\Report

1. 按兩下&#x200B;**[!UICONTROL ReportServer.exe]**。
1. 若要確認[!DNL Report Server]是否正常運作，請按一下「**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**」。 此命令序列可能因您使用的Windows版本而異。
1. 在服務清單中，找到[!DNL Report Server]的條目，並確認其狀態為「啟動」且其啟動類型為「自動」。
1. 執行以下操作以指定將在其下執行[!DNL Report Server]的用戶帳戶：

   1. 按兩下&#x200B;**[!UICONTROL Report Server]**&#x200B;以開啟[!DNL Properties]窗口。

   1. 選擇&#x200B;**[!UICONTROL Log On]**&#x200B;頁簽。
   1. 選擇&#x200B;**[!UICONTROL This account]**&#x200B;單選按鈕。
   1. 鍵入或瀏覽帳戶名稱。 此帳戶必須擁有存取儲存產生報表之位置的權限。

      >[!NOTE]
      >
      >如果[!DNL Report Server]以Microsoft Excel（[!DNL .xls]或[!DNL .xlsx]）檔案分發報表，請確保帳戶也具有運行Microsoft Excel的權限。

   1. 輸入並確認帳戶的密碼。
   1. 按一下 **[!UICONTROL OK]**。

1. 按一下右鍵[!DNL Report Server]服務，然後選擇&#x200B;**[!UICONTROL Restart]**&#x200B;以在您指定的帳戶下重新啟動服務。
1. 要檢查[!DNL Report Server]在啟動過程中是否遇到任何錯誤，請按一下「**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**」。 此命令序列可能因您使用的Windows版本而異。

   1. 在[!DNL Event Viewer]窗口的左窗格中，選擇應用程式日誌。
   1. 在右窗格中，查找[!DNL Source]列中包含Adobe的事件。
   1. 如果Adobe中發現錯誤，請按兩下錯誤以顯示[!DNL Event Properties]窗口。 此窗口提供有關錯誤的詳細資訊。

      >[!NOTE]
      >
      >[!DNL Report Server]服務啟動後，檔案[!DNL ReportServer.log]會建立在報表伺服器[!DNL Trace]目錄中。 此檔案對於疑難排解[!DNL Report Server]的問題也很實用。

您已完成[!DNL Report Server]的安裝。 [!DNL Report Server] 設計為持續執行。如果重新啟動電腦，[!DNL Report Server]將自動重新啟動。 如果需要手動啟動和停止[!DNL Report Server]，可以使用Windows中的[!DNL Services]控制面板執行此操作。
