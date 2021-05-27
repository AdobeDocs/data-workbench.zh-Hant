---
description: 產生報表後，Report會根據其Report.cfg檔案中的設定，在集中分發報表。
title: 分發報表
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# 分發報表{#distributing-reports}

產生報表後，Report會根據其Report.cfg檔案中的設定，在集中分發報表。

[!DNL Report] 可讓您使用下列方法在集合中分發報表：

* **電子郵件：** 若要透過電子郵件( [!DNL .png] 內嵌或附件)以Excel檔案、檔案或縮圖形式分發報表，請在報表集的檔案中指定「郵件報表」 [!DNL Report.cfg] 參數。該集中的所有報表都會以一則訊息傳送給指定的收件者。

* **共用目錄：** 若要將報表以Excel檔案、檔 [!DNL .png] 案或縮圖的形式分發至共用目錄，請在報表集檔案的「輸出根」參數中指定 [!DNL Report.cfg] 目錄。

* **Reporting Portal:** Reporting Portal可讓您透過網頁瀏覽器檢視報表。Adobe的[!DNL Report Portal]顯示以Excel或[!DNL .png]檔案產生的報表，但不顯示以縮圖([!DNL .jpg])產生的報表。 要將報表分發到門戶，請在報表集[!DNL Report.cfg]檔案的「輸出根」參數中指定用於門戶的Web伺服器的文檔根。 有關安裝和使用[!DNL Report Portal]的詳細資訊，請參閱[使用Report Portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>要讀取[!DNL Report]當前支援的輸出，您必須有一個能夠以所需格式顯示報告的應用程式。 例如，要查看[!DNL .xlsx]檔案，必須有Microsoft Excel 2007或更高版本。

您也可以使用這些產生和分送選項的組合。 例如，如果您設定[!DNL Report Types]參數以產生作為Excel和[!DNL .png]檔案的報表集，然後設定[!DNL Mail Report]和[!DNL Output Root]參數，則該集中的所有報表都會分發至指定的輸出目錄（可能在入口網站中檢視），並在一封電子郵件中以電子郵件傳送給收件者。

如需設定報表集的步驟，請參閱[使用報表集](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)。 如需特定[!DNL Report.cfg]參數的詳細資訊，請參閱[Report.cfg參數](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
