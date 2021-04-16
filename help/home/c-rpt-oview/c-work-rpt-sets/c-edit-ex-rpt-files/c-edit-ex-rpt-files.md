---
description: 使用Worktop或文字編輯器編輯現有Report.cfg檔案的步驟。
title: 編輯現有的 Report.cfg 檔案
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
exl-id: 69038c0c-bb01-4e61-aad6-1be0bdec8a6d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 2%

---

# 編輯現有的 Report.cfg 檔案{#editing-existing-report-cfg-files}

使用Worktop或文字編輯器編輯現有Report.cfg檔案的步驟。

>[!NOTE]
>
>* 您必須線上上工作才能編輯[!DNL Report.cfg]檔案。 若要線上上工作，請在[!DNL Worktop]中，以滑鼠右鍵按一下標題列，然後按一下&#x200B;**[!UICONTROL Work Online]**。
   >
   >
* 如果[!DNL Report.cfg]檔案中的&#x200B;**[!UICONTROL Allow Report Regeneration]**&#x200B;參數設為[!DNL True]，當您變更該檔案並將該檔案儲存回伺服器時，[!DNL Report]會自動重新產生該集中的報表。 雖然會重新產生報表，但不會透過電子郵件重新傳送報表。 如需執行此動作的步驟，請參閱[依電子郵件重新傳送報表](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607)。

>



您可以從[!DNL Worktop]中編輯現有的[!DNL Report.cfg]或使用文本編輯器。

使用[!DNL Worktop]的[!DNL Reports]標籤編輯[!DNL Report.cfg]檔案時，您只能編輯檔案中已存在的參數、向量和向量項目。 如果您需要將參數或向量新增至檔案，則必須使用文字編輯器（例如記事本）加以編輯。

* [若要使用Worktop編輯現有的Report.cfg](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [若要使用文字編輯器編輯現有的Report.cfg](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## 若要使用Worktop {#section-7bce3bca006149c79be7678430f21945}編輯現有的Report.cfg

>[!NOTE]
>
>您必須線上上工作，才能編輯[!DNL Worktop]中的[!DNL Report.cfg]。

1. 在資料工作台的[!DNL Reports]標籤上，為您要設定的報表集選取子資料夾（標籤或下拉式子目錄）。
1. 按一下「**[!UICONTROL Report.cfg]**」。此報告集的[!DNL Report.cfg]參數隨即顯示。

1. 視需要編輯設定參數。 如需這些參數的詳細資訊，請參閱[Report.cfg參數](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
1. 按一下右鍵參數頂部的&#x200B;**[!UICONTROL Report.cfg (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save to]*****[!UICONTROL server location]**>*以保存檔案。

## 若要使用文字編輯器{#section-06f3d2a8d7f34bc2841180caf10a1eb7}編輯現有的Report.cfg

1. 在工作區中按一下滑鼠右鍵，然後按一下「**[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**」以開啟[!DNL Reports Manager]。

1. 按一下報表集的資料夾。
1. 按一下右鍵此報告集的[!DNL Report.cfg]旁邊的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。

1. 在[!DNL User]欄中，以滑鼠右鍵按一下此報表集[!DNL Report.cfg]旁的核取標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 將開啟[!DNL Report.cfg]檔案。

   [Configure the Report Set](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)中顯示的範例[!DNL Report.cfg]預設僅包含[!DNL Report.cfg]檔案中包含的參數。 以下示例包括可用於[!DNL Report.cfg]檔案的所有參數，可用作參數項的模型：

   ```
   Attachments = vector: 1 items
     0 = Attachment:
       FileName = string: c:\\myimage.jpg
       Content Type = string: image/jpeg
   Alert Threshold = int: 0
   Allow Report Regeneration = bool: true
   Color Set = int: 1
   Command To Execute = string: 
   Default Excel Template = string: 
   Dimension Name = string: 
   Email Only If Perfect = bool: false
   End Date = string: 
   Every = string: month
   Excel Watchdog Timeout (seconds) = double: 300.0
   Filter Formula = string: 
   Gamma Correction = double: 1
   Hide Logos = bool: false
   Lookup File = string: 
   Mail Report = MailReport: 
     Body XSL Template = string: 
     Recipients = vector: 0 items
     SMTP Server = SmtpServerInfo: 
       Address = string: 
       Password = string: 
       User = string: 
     Sender Address = string: 
     Sender Name = string: 
     Subject = string: 
   Notification Only = bool: false
   Output Root = string: 
   Report Types = vector: 3 items
     0 = string: thumbnail
     1 = string: png
     2 = string: excel
   Start Date = string: 7/1/06 19:16 EDT
   Thumbnail X = int: 240
   Thumbnail Y = int: 180
   Top N Metric = string: 
   Top N Value = int: 0
   Use Local Sample Only = bool: false
   Workspace Path = string: 
   ```

1. 視需要編輯設定參數。 如需這些參數的詳細資訊，請參閱[Report.cfg參數](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
1. 儲存並關閉檔案。
1. 在[!DNL Reports Manager]中，按一下右鍵[!DNL Report.cfg]檔案[!DNL User]列中的複選標籤，然後選擇&#x200B;**[!UICONTROL Save to]*****[!UICONTROL profile name]***。
