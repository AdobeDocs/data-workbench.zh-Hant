---
description: 要盡快檢測系統和應用程式錯誤，並在它們導致重大問題或中斷之前解決這些錯誤，您應定期監控事件日誌。
solution: Analytics
title: 監控錯誤事件
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 5%

---


# 監控錯誤事件{#monitoring-events-for-errors}

要盡快檢測系統和應用程式錯誤，並在它們導致重大問題或中斷之前解決這些錯誤，您應定期監控事件日誌。

**建議頻率：** 每5-10分鐘

若要監控您的Adobe伺服器軟體產品，您可以設定自動化管理工具來監控您的事件記錄，以找出來源「Adobe」的錯誤，然後提醒適當人員注意可能需要干預的問題。

在Windows中，應用程式錯誤訊息會輸出至Windows中的應用程式事件記錄檔，您可使用Windows事件檢視器來存取該記錄檔。 在Unix中，應用程式錯誤消息使用LOG_DAEMON工具輸出到Unix系統日誌。

**若要開啟Windows事件檢視器**

* Click **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

