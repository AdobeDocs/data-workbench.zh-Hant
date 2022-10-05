---
description: 透過電子郵件重新傳送報表的步驟。
title: 依電子郵件重新傳送報表
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# 依電子郵件重新傳送報表{#resending-reports-by-email}

{{eol}}

透過電子郵件重新傳送報表的步驟。

若 **[!UICONTROL Allow Report Regeneration]** 參數 [!DNL Report.cfg] 檔案設為 [!DNL True]，當您對 [!DNL Report.cfg] 檔案並將該檔案儲存回伺服器，報表伺服器會自動重新產生該集中的報表。 它不會透過電子郵件重新傳送報表。

1. 在 [!DNL Reports] 頁簽，為要重新發送的報表集選擇子資料夾（頁簽或下拉子目錄）。
1. 按一下「**[!UICONTROL Report.cfg]**」。的參數 [!DNL Report.cfg] 顯示。
1. 變更 **[!UICONTROL Start Date]** 參數重新發送報告的將來時間。
1. 按一下滑鼠右鍵以儲存檔案 **[!UICONTROL Report.cfg (modified)]** ，然後按一下 **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
此集中的報表會重新產生，並透過電子郵件重新傳送給指定的收件者。
