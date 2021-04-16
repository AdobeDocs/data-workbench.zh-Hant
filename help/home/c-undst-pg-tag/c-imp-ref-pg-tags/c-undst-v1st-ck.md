---
description: 網站使用Cookie來唯一識別您網站的訪客，並追蹤其隨時間的行為。
title: 瞭解 v1st Cookie
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# 瞭解 v1st Cookie{#understanding-the-v-st-cookie}

網站使用Cookie來唯一識別您網站的訪客，並追蹤其隨時間的行為。

當特定瀏覽器（視為訪客）第一次提出您網站的要求時，[!DNL Sensor]會與您的網頁伺服器搭配使用，以設定永久性Cookie,cs(cookie)(v1st)，在系統內部會解譯為x-trackingid。 此永久性Cookie除了設定您的網站可能設定的任何其他Cookie外，也會加以設定。 此Cookie可最佳化您在多個作業期間追蹤訪客的能力，讓您進行許多原本無法進行的分析類型。

[!DNL Sensor] 在Cookie中指派64位元數值金鑰，以識別提出網站要求的新訪客為唯一識別碼。當[!DNL Sensor]看到來自瀏覽器的請求時，會檢查請求資料中是否存在「cs(cookie)(v1st)」（由[!DNL Sensor]設定的第一方永久性Cookie）。 如果cs(cookie)(v1st)不存在，[!DNL Sensor]會透過您的網頁伺服器通知瀏覽器設定。 與其他解決方案不同，[!DNL Sensor]可在訪客的第一個請求上設定此Cookie。

以下是Web伺服器在第一次要求您的網站時，以[!DNL Sensor]方向傳送至瀏覽器的標準永久性Cookie標題。 如果需要不同的名稱或到期日，可以在配置時定義格式。 例如：

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

此Cookie僅設定一次，即是該訪客對您網站提出的第一個要求。 然後，當瀏覽器在未來每次提出您網站的請求（頁面或內嵌物件請求）時，都會從該訪客收集此資料。 Cookie的大小非常小，可將每次從瀏覽器傳送至網站時，傳送至伺服器的頻寬量降至最低。

接受永久性Cookie由瀏覽器自行決定。 大部分的網頁使用者都瞭解Cookie的功能，並且也瞭解第一方Cookie為他們提供了有價值的好處，讓網站內容可依其偏好自訂。 這些第一方Cookie不會受到常用瀏覽器的預設安全性設定所封鎖。 如果使用者確實選擇封鎖第一方Cookie，其頁面檢視請求仍會記錄，但這些請求的測量資料無法可靠地關聯至網站上的特定訪客或其作業。 許多網站（尤其是複雜的動態網站）都已使用第一方Cookie，這在許多情況下是讓Web應用程式為訪客運作的必要工具。 從永續性Cookie後退的步驟是作業Cookie，可讓一系列請求結合到作業中，但不允許作業間訪客追蹤。 [!DNL Site] 能夠根據工作階段Cookie或IP編號對訪客資料進行作業，但這兩種方法都會明顯降低分析的類型和值，而可與任何其他Web活動分析和報 [!DNL Site] 告系統一起進行。
