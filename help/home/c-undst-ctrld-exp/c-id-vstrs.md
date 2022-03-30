---
description: 站點的典型配置使用cookie來唯一標識網站的訪問者並跟蹤他們隨時間的變化的行為。
solution: Analytics
title: Site 如何識別訪客？
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# Site 如何識別訪客？{#how-does-site-identify-visitors}

站點的典型配置使用cookie來唯一標識網站的訪問者並跟蹤他們隨時間的變化的行為。

第一次特定瀏覽器（視為訪問者）請求您的網站時， [!DNL Sensor] 與Web伺服器一起使用以設定永久cookie（預設情況下） [!DNL cs(cookie)(v1st)])，在系統內部解釋為 [!DNL x-trackingid]。 此Cookie僅設定一次，即在該訪問者首次向您的網站發出請求時。 然後，在瀏覽器將來每次向您的網站發出請求（頁面或嵌入對象請求）時，都會從該訪問者收集該資訊。

接受永久Cookie由瀏覽器自行決定。 如果用戶確實選擇阻止持久性Cookie，則其頁面視圖請求仍會被記錄，但來自這些請求的測量資料不會與特定訪問者或他們在網站上的會話相關，除非您實施了訪問者標識的替代方法，如在IP和UserAgent欄位上使用哈希轉換。

>[!NOTE]
>
>只有在資料集中才能分析站點實驗，其中唯一使用的訪問者識別方法是 [!DNL Sensor] 設定永久cookie方法。 運行在J2EE伺服器（JBoss、Tomcat、WebLogic和WebSphere）上的感測器不支援受控實驗。

在受控實驗期間，不接受cookie的用戶可以從點擊到下一點，放在不同的實驗組中。 僅當在「斷開會話過濾器」處於關閉狀態時執行test分析時，才會出現此問題 [!DNL Insight]，該Adobe不推薦。

有關中斷會話篩選器的詳細資訊，請參閱* [!DNL Insight] 使用手冊*。

如果訪問者在實驗期間清除cookie，則會為訪問者分配新cookie，並可能會將其分配給其他組。 由於Adobe將訪問者標識為新訪問者，因此該實驗不會失效。
