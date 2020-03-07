---
description: 產生報表後，報表會根據其Report.cfg檔案中的設定，在集合中分發報表。
solution: Analytics
title: 分發報表
topic: Data workbench
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 分發報表{#distributing-reports}

產生報表後，報表會根據其Report.cfg檔案中的設定，在集合中分發報表。

[!DNL Report] 可讓您使用下列方法，在集合中分發報表：

* **電子郵件：** 若要透過電子郵件( [!DNL .png] 串聯或附件)將報表分發為Excel檔案、檔案或縮圖，請在報表集的檔案中指定「郵件報表」參 [!DNL Report.cfg] 數。 該集中的所有報表都會以電子郵件傳送給指定的收件者。

* **共用目錄：** 若要將報表分發為Excel檔 [!DNL .png] 案、檔案或縮圖至共用目錄，請在報表集檔案的「輸出根目錄」參數中指定目 [!DNL Report.cfg] 錄。

* **報告入口網站：** 報告入口網站可讓您透過網頁瀏覽器檢視報告。 Adobe的報表 [!DNL Report Portal] 會顯示為Excel或檔案所產生， [!DNL .png] 但不會顯示為縮圖( [!DNL .jpg])所產生的報表。 若要將報表分發至入口網站，請在報表集檔案的「輸出根」參數中，指定用於入口網站的Web伺服器的檔案根 [!DNL Report.cfg] 目錄。 如需安裝和使用的詳細資訊，請 [!DNL Report Portal]參閱使 [用報表入口網站](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>若要讀取目前支援的輸 [!DNL Report]出，您必須擁有能夠以所需格式顯示報表的應用程式。 例如，若要檢視 [!DNL .xlsx] 檔案，您必須有Microsoft Excel 2007或更新版本。

您也可以結合使用這些產生和散發選項。 例如，如果您設定參 [!DNL Report Types] 數以產生報表集為Excel和檔案，然後設定 [!DNL .png][!DNL Mail Report][!DNL Output Root] and參數，則該集中的所有報表都會分發至指定的輸出目錄（可能在入口網站中檢視），並以電子郵件寄送給收件者。

如需設定報表集的步驟，請參閱使 [用報表集](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)。 如需特定參數的詳細資 [!DNL Report.cfg] 訊，請參 [閱Report.cfg參數](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
