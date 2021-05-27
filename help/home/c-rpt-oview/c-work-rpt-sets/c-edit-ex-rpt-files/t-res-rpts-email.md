---
description: 透過電子郵件重新傳送報表的步驟。
title: 依電子郵件重新傳送報表
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# 依電子郵件重新傳送報表{#resending-reports-by-email}

透過電子郵件重新傳送報表的步驟。

如果[!DNL Report.cfg]檔案中的&#x200B;**[!UICONTROL Allow Report Regeneration]**&#x200B;參數設為[!DNL True]，當您對[!DNL Report.cfg]檔案進行變更並將該檔案儲存回伺服器時，報表伺服器會自動重新產生該集中的報表。 它不會透過電子郵件重新傳送報表。

1. 在[!DNL Reports]標籤中，選取您要重新傳送之報表集的子資料夾（索引標籤或下拉式子目錄）。
1. 按一下「**[!UICONTROL Report.cfg]**」。此報表集的[!DNL Report.cfg]參數隨即顯示。
1. 將&#x200B;**[!UICONTROL Start Date]**&#x200B;參數變更為您要重新發送報表的未來時間。
1. 以滑鼠右鍵按一下參數頂端的&#x200B;**[!UICONTROL Report.cfg (modified)]**，然後按一下&#x200B;**[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*以儲存檔案。
此集中的報表會重新產生，並透過電子郵件重新傳送給指定的收件者。
