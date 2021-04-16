---
description: 網站的典型組態使用Cookie來唯一識別您網站的訪客，並追蹤其隨時間的行為。
solution: Analytics,Analytics
title: Site 如何識別訪客？
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# Site 如何識別訪客？{#how-does-site-identify-visitors}

網站的典型組態使用Cookie來唯一識別您網站的訪客，並追蹤其隨時間的行為。

當特定瀏覽器（視為訪客）第一次提出您網站的要求時，[!DNL Sensor]會與您的網頁伺服器搭配使用，以設定永續性Cookie（依預設為[!DNL cs(cookie)(v1st)]），並在系統內部解譯為[!DNL x-trackingid]。 此Cookie僅設定一次，即是該訪客在第一次向您的網站提出要求時。 然後，當瀏覽器在日後每次提出您網站的要求（頁面或內嵌物件要求）時，都會從該訪客收集此資料。

接受永久性Cookie由瀏覽器自行決定。 如果使用者選擇封鎖永久性Cookie，其頁面檢視請求仍會記錄，但是來自這些請求的測量資料不會關聯至網站上的特定訪客或其工作階段，除非您實作訪客識別的替代方法，例如在IP和UserAgent欄位上使用雜湊轉換。

>[!NOTE]
>
>網站實驗只能在使用中唯一訪客識別方法為[!DNL Sensor]設定永久性Cookie方法的資料集中進行分析。 在J2EE伺服器（JBoss、Tomcat、WebLogic和WebSphere）上執行的感測器不支援控制實驗。

在受控實驗期間，不接受Cookie的使用者可以從點選到點選，放在不同的實驗群組中。 只有當您在[!DNL Insight]中關閉「中斷的作業階段篩選」時執行測試分析，才會發生此問題，不建議使用該Adobe。

有關中斷會話過濾器的詳細資訊，請參閱* [!DNL Insight]使用手冊*。

如果訪客在實驗期間清除Cookie，則會為訪客指派新Cookie，並可能指派給其他群組。 由於Adobe會將訪客識別為新訪客，因此實驗不會無效。
