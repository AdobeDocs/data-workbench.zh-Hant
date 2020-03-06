---
description: 使用Worktop或文字編輯器編輯現有Report.cfg檔案的步驟。
solution: Analytics
title: 編輯現有的Report.cfg檔案
topic: Data workbench
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 編輯現有的Report.cfg檔案{#editing-existing-report-cfg-files}

使用Worktop或文字編輯器編輯現有Report.cfg檔案的步驟。

>[!NOTE]
>
>* 您必須線上上工作才能編輯 [!DNL Report.cfg] 檔案。 若要線上上工作，請在標 [!DNL Worktop]題列上按一下滑鼠右鍵，然後按一下 **[!UICONTROL Work Online]**。
   >
   >
* 如果 **[!UICONTROL Allow Report Regeneration]** 檔案中的 [!DNL Report.cfg] 參數設為 [!DNL True]，當您變更該檔案並將該檔案儲存回伺服器時， [!DNL Report] 會自動重新產生該集中的報表。 雖然會重新產生報表，但不會透過電子郵件重新傳送報表。 如需執行此動作的步驟，請參閱「依 [電子郵件重新傳送報表」](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607)。
>



您可以從或使用文 [!DNL Report.cfg] 字編輯 [!DNL Worktop] 器編輯現有文字。

使用 [!DNL Report.cfg] 的頁籤編 [!DNL Reports] 輯檔案 [!DNL Worktop] 時，您只能編輯檔案中已存在的參數、向量和向量項。 如果您需要將參數或向量新增至檔案，則必須使用文字編輯器（例如記事本）加以編輯。

* [若要使用Worktop編輯現有的Report.cfg](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [若要使用文字編輯器編輯現有的Report.cfg](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## 若要使用Worktop編輯現有的Report.cfg {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>您必須線上上工作，才能從 [!DNL Report.cfg] 中編輯 [!DNL Worktop]。

1. 在資料工作台的標 [!DNL Reports] 簽上，為您要設定的報表集選取子資料夾（標籤或下拉式子目錄）。
1. 按一下 **[!UICONTROL Report.cfg]**. 此報表集 [!DNL Report.cfg] 的參數隨即顯示。

1. 視需要編輯設定參數。 如需這些參數的詳細資訊，請參 [閱Report.cfg參數](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
1. 以滑鼠右鍵按一下參 **[!UICONTROL Report.cfg (modified)]** 數頂端的檔案，然後按一下 **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>以儲存檔案&#x200B;*。

## 若要使用文字編輯器編輯現有的Report.cfg {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. 在工作 [!DNL Reports Manager] 區中按一下滑鼠右鍵，然後按一下 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** >以開啟 **[!UICONTROL Reports Manager]**。

1. 按一下報表集的資料夾。
1. 在此報表集旁的核取標籤上按一 [!DNL Report.cfg] 下滑鼠右鍵，然後按一下 **[!UICONTROL Make Local]**。

1. 在欄中， [!DNL User] 以滑鼠右鍵按一下此報表集旁 [!DNL Report.cfg] 的核取標籤，然後按 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 檔案 [!DNL Report.cfg] 隨即開啟。

   預設情 [!DNL Report.cfg] 況下，設 [定報表集中所示的範例僅包含](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)[!DNL Report.cfg] 檔案中的參數。 下面的示例包括可用於檔案的所有可 [!DNL Report.cfg] 用參數，這些參數可用作參數項的模型：

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

1. 視需要編輯設定參數。 如需這些參數的詳細資訊，請參 [閱Report.cfg參數](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
1. 儲存並關閉檔案。
1. 在中， [!DNL Reports Manager]按一下右鍵檔案列中的複選 [!DNL User] 標籤並 [!DNL Report.cfg] 選擇 **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*。

