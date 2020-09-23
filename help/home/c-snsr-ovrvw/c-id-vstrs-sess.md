---
description: 從Web伺服器收集事件資料時，Sensor會自動為每個包含小型隨機識別碼的訪客設定永久性Cookie，而不會擷取任何個人識別資訊。
solution: Analytics
title: Sensor 如何識別訪客和工作階段？
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---


# Sensor 如何識別訪客和工作階段？{#how-does-sensor-identify-visitors-and-sessions}

從Web伺服器收集事件資料時，Sensor會自動為每個包含小型隨機識別碼的訪客設定永久性Cookie，而不會擷取任何個人識別資訊。

此Adobe Cookie用於識別獨特訪客及其所有相關工作階段。

依預設， [!DNL Sensor][!DNL Sensor] 會從每個HTTP標題中擷取所有W3C擴充記錄檔格式欄位，但您可以設定擷取用戶端與伺服器間傳輸的任何標題。 如需檔案中所收集之事件資料欄位的 [!DNL Sensor] 詳細 [!DNL .vsl] 資訊，請 [參閱事件資料記錄欄位](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)。

有些訪客的瀏覽器不會永久儲存Cookie，而且極少數訪客的瀏覽器完全不接受Cookie（甚至作業Cookie）。 即使這些頁面僅佔網站總流量的一小部分，但如果此類訪客的每個頁面檢視都被錯誤計算為整個作業階段，可能會造成重大誤算，就像某些記錄檔分析軟體所做的那樣。 Adobe可讓您分析有無使用Cookie的訪客，以解決此問題。

有關中斷會話過濾器的詳細資訊，請參 *閱資料工作台感測器指南*。
