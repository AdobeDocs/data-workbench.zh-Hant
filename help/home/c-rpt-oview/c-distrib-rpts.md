---
description: 產生報表後，Report會根據其Report.cfg檔案中的設定，在集中分發報表。
title: 分發報表
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# 分發報表{#distributing-reports}

{{eol}}

產生報表後，Report會根據其Report.cfg檔案中的設定，在集中分發報表。

[!DNL Report] 可讓您使用下列方法在集合中分發報表：

* **電子郵件：** 若要以Excel檔案分發報表， [!DNL .png] 檔案或透過電子郵件的縮圖（內聯或作為附件），請在報表集的「郵件報表」參數中指定 [!DNL Report.cfg] 檔案。 該集中的所有報表都會以一則訊息傳送給指定的收件者。

* **共用目錄：** 若要以Excel檔案分發報表， [!DNL .png] 檔案或縮圖到共用目錄，請在報表集的「輸出根」參數中指定目錄 [!DNL Report.cfg] 檔案。

* **Reporting Portal:** 報表入口網站可讓您透過網頁瀏覽器檢視報表。 Adobe [!DNL Report Portal] 顯示以Excel或 [!DNL .png] 檔案，但不是以縮圖( [!DNL .jpg])。 要將報表分發到門戶，請在報表集的「輸出根」參數中指定用於門戶的Web伺服器的文檔根 [!DNL Report.cfg] 檔案。 如需安裝和使用的詳細資訊 [!DNL Report Portal]，請參閱 [使用Report Portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>讀取當前支援的輸出 [!DNL Report]，您必須有能夠以所需格式顯示報表的應用程式。 例如，若要檢視 [!DNL .xlsx] 檔案時，您必須有Microsoft Excel 2007或更新版本。

您也可以使用這些產生和分送選項的組合。 例如，若您設定 [!DNL Report Types] 參數，以產生Excel和 [!DNL .png] 檔案，然後設定 [!DNL Mail Report]和 [!DNL Output Root] 參數中，該集合中的所有報表都會分發至指定的輸出目錄（可能要在入口網站中檢視），並以一封電子郵件寄送給收件者。

如需設定報表集的步驟，請參閱 [使用報表集](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). 如需特定 [!DNL Report.cfg] 參數，請參閱 [Report.cfg參數](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
