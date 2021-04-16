---
description: 產生報表後，報表會根據其Report.cfg檔案中的設定，在集合中分發報表。
title: 分發報表
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# 分發報表{#distributing-reports}

產生報表後，報表會根據其Report.cfg檔案中的設定，在集合中分發報表。

[!DNL Report] 可讓您使用下列方法，在集合中分發報表：

* **電子郵件：** 若要透過電子郵件( [!DNL .png] 串聯或附件)以Excel檔案、檔案或縮圖形式分發報表，請在報表集的檔案中指定「郵件報表」參 [!DNL Report.cfg] 數。該集中的所有報表都會以電子郵件傳送給指定的收件者。

* **共用目錄：** 若要將報表分發為Excel檔案、 [!DNL .png] 檔案或縮圖，請在報表集檔案的「輸出根目錄」參數中指定目 [!DNL Report.cfg] 錄。

* **報告入口網** 站：報告入口網站可讓您透過網頁瀏覽器檢視報告。Adobe的[!DNL Report Portal]會顯示以Excel或[!DNL .png]檔案產生的報表，但不會顯示以縮圖([!DNL .jpg])產生的報表。 若要將報表分發至入口網站，請在報表集[!DNL Report.cfg]檔案的「輸出根」參數中，指定用於入口網站的Web伺服器檔案根目錄。 有關安裝和使用[!DNL Report Portal]的詳細資訊，請參閱[使用報告門戶](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>若要讀取[!DNL Report]目前支援的輸出，您必須擁有能夠以所需格式顯示報表的應用程式。 例如，若要檢視[!DNL .xlsx]檔案，您必須有Microsoft Excel 2007或更新版本。

您也可以結合使用這些產生和散發選項。 例如，如果您設定[!DNL Report Types]參數以產生報表集為Excel和[!DNL .png]檔案，然後設定[!DNL Mail Report]和[!DNL Output Root]參數，該集中的所有報表都會分發至指定的輸出目錄（可能在入口網站中檢視），並以電子郵件寄送給收件者。

如需設定報表集的步驟，請參閱[使用報表集](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)。 如需特定[!DNL Report.cfg]參數的詳細資訊，請參閱[Report.cfg參數](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
