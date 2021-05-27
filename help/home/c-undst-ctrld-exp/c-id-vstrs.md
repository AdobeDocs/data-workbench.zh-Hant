---
description: 一般的網站設定會使用Cookie來唯一識別來到您網站的訪客，並追蹤其在一段時間內的行為。
solution: Analytics,Analytics
title: Site 如何識別訪客？
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# Site 如何識別訪客？{#how-does-site-identify-visitors}

一般的網站設定會使用Cookie來唯一識別來到您網站的訪客，並追蹤其在一段時間內的行為。

當特定瀏覽器（視為訪客）首次提出網站請求時，[!DNL Sensor]會與您的網站伺服器合作以設定永久性Cookie（依預設為[!DNL cs(cookie)(v1st)]），而在系統內部解譯為[!DNL x-trackingid]。 此Cookie只會在該訪客對您網站提出的第一次要求時設定一次。 接著，當瀏覽器日後每次提出您網站的請求（頁面或內嵌物件請求）時，都會從該訪客收集資料。

接受永久性Cookie由瀏覽器決定。 如果使用者選擇封鎖永久性Cookie，其頁面檢視請求仍會記錄，但來自這些請求的測量資料不會與特定訪客或其網站上的工作階段產生關聯，除非您實作替代的訪客身分識別方法，例如在IP和UserAgent欄位上使用雜湊轉換。

>[!NOTE]
>
>只有在使用中唯一的訪客身分識別方法是[!DNL Sensor]設定永久性Cookie方法的資料集中，才能分析網站實驗。 在J2EE伺服器（JBoss、Tomcat、WebLogic和WebSphere）上運行的感測器不支援受控實驗。

在受控實驗期間，不接受Cookie的使用者可能會被置於不同的實驗群組中，從一次點按到下一次。 只有當您在[!DNL Insight]中關閉「中斷工作階段篩選器」的情況下執行測試分析，才會發生此問題，不建議使用此Adobe。

如需「中斷工作階段篩選」的詳細資訊，請參閱* [!DNL Insight]使用手冊*。

如果訪客在實驗期間清除Cookie，則會為訪客指派新Cookie，且可能會指派給不同群組。 由於Adobe會將訪客識別為新訪客，因此實驗不會失效。
