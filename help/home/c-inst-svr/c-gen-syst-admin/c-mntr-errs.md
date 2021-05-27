---
description: 要盡快檢測系統和應用程式錯誤，並在系統和應用程式錯誤導致重大問題或中斷之前解決這些錯誤，您應定期監視事件日誌。
title: 監控錯誤事件
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
exl-id: 88f48594-5c73-4ae3-8014-b8543e689426
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 5%

---

# 監控錯誤事件{#monitoring-events-for-errors}

要盡快檢測系統和應用程式錯誤，並在系統和應用程式錯誤導致重大問題或中斷之前解決這些錯誤，您應定期監視事件日誌。

**建議頻率：** 每5-10分鐘

要監視Adobe伺服器軟體產品，可以設定自動管理工具來監視事件日誌中是否有源「Adobe」錯誤，然後提醒適當的人員注意可能需要干預的問題。

在Windows中，應用程式錯誤消息將輸出到Windows中的應用程式事件日誌，您可以使用Windows事件查看器訪問該日誌。 在Unix中，應用程式錯誤消息將使用LOG_DAEMON工具輸出到Unix系統日誌。

**開啟Windows事件查看器**

* 按一下「**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**」。
