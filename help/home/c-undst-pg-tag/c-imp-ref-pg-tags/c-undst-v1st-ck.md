---
description: 網站使用Cookie來唯一識別來到您網站的訪客，並追蹤其在一段時間內的行為。
title: 瞭解 v1st Cookie
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# 瞭解 v1st Cookie{#understanding-the-v-st-cookie}

網站使用Cookie來唯一識別來到您網站的訪客，並追蹤其在一段時間內的行為。

當特定瀏覽器（視為訪客）首次提出網站請求時，[!DNL Sensor]會與您的網站伺服器合作設定永久性Cookie cs(cookie)(v1st)，在系統內部解譯為x-trackingid。 此永久性Cookie是除了您的網站可能設定的任何其他Cookie外設定的。 此Cookie會最佳化您在多個工作階段中追蹤訪客的能力，以啟用原本不可能的許多分析類型。

[!DNL Sensor] 在cookie中指派64位元數值金鑰，以識別將網站請求當作唯一識別碼的新訪客。當[!DNL Sensor]看見來自瀏覽器的請求時，會檢查請求資料中是否存在「cs(cookie)(v1st)」（由[!DNL Sensor]設定的第一方永久性Cookie）。 如果cs(cookie)(v1st)不存在，[!DNL Sensor]會透過您的網頁伺服器，告訴瀏覽器進行設定。 與其他解決方案不同，[!DNL Sensor]可以在訪客的第一個要求上設定此Cookie。

以下是網站伺服器第一次要求瀏覽器時，以[!DNL Sensor]方向傳送至瀏覽器的標準永久性Cookie標題。 如果需要不同的名稱或到期日，可在設定時定義格式。 例如：

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

此Cookie只會在該訪客對您的網站提出的第一次要求時設定一次。 接著，系統會在瀏覽器日後每次提出您網站的請求（頁面或內嵌物件請求）時，從該訪客收集這些資料。 Cookie的大小非常小，可將從瀏覽器傳送至您網站的每個要求時，用於將其傳送至伺服器的頻寬量降至最低。

接受永久性Cookie由瀏覽器決定。 大部分的網頁使用者都了解Cookie的功能，並認識到第一方Cookie可為他們提供實用優勢，讓網站內容可依其偏好自訂。 熱門瀏覽器的預設安全設定不會封鎖這些第一方Cookie。 如果使用者選擇封鎖第一方Cookie，其頁面檢視請求仍會記錄，但來自這些請求的測量資料無法可靠地關聯至網站上的特定訪客或其工作階段。 許多網站（尤其是複雜的動態網站）已使用第一方Cookie，這在許多情況下是讓Web應用程式為訪客運作所必要的。 從永久性Cookie往後的步驟是工作階段Cookie，可將一系列請求結合到工作階段中，但不允許工作階段間訪客追蹤。 [!DNL Site] 能夠根據工作階段cookie或IP號碼將訪客資料設為工作階段，但兩種方法都大幅削弱了可透過或任何其他網站活動分析和報告 [!DNL Site] 系統進行之分析的類型和價值。
