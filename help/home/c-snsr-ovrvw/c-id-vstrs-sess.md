---
description: 從Web伺服器收集事件資料時，Sensor會自動為每個包含小型隨機識別碼的訪客設定永久性Cookie，而不擷取任何個人識別資訊。
title: Sensor 如何識別訪客和工作階段？
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
exl-id: f5781ed6-ac83-4a8e-b412-8966f8c39c41
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# Sensor 如何識別訪客和工作階段？{#how-does-sensor-identify-visitors-and-sessions}

從Web伺服器收集事件資料時，Sensor會自動為每個包含小型隨機識別碼的訪客設定永久性Cookie，而不擷取任何個人識別資訊。

此AdobeCookie可用來識別不重複訪客及其所有相關工作階段。

預設情況下， [!DNL Sensor]從每個HTTP標頭中捕獲所有W3C擴展日誌檔案格式欄位，但您可以配置[!DNL Sensor]以捕獲在客戶端和伺服器之間傳輸的任何標頭。 有關[!DNL .vsl]檔案中[!DNL Sensor]收集的事件資料欄位的資訊，請參閱[事件資料記錄欄位](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)。

有些訪客的瀏覽器不會持續儲存Cookie，而極少數的訪客的瀏覽器完全不接受Cookie（甚至工作階段Cookie）。 即使這些量度僅佔網站總流量的一小部分，但如果此訪客的每個頁面檢視都計為整個工作階段（某些記錄檔分析軟體已這麼做），則可能會導致重大誤計。 Adobe可讓您分析有無使用Cookie的訪客，借此解決此問題。

有關「中斷會話」篩選器的詳細資訊，請參閱&#x200B;*Data Workbench感測器指南*。
