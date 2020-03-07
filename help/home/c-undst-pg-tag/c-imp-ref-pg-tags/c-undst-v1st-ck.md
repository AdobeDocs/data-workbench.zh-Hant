---
description: 網站使用Cookie來唯一識別您網站的訪客，並追蹤其隨時間的行為。
solution: Analytics
title: 瞭解v1st Cookie
topic: Data workbench
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 瞭解v1st Cookie{#understanding-the-v-st-cookie}

網站使用Cookie來唯一識別您網站的訪客，並追蹤其隨時間的行為。

特定瀏覽器（視為訪客）第一次提出您網站的要求時，會與您的網頁伺服器搭配運作，以設定永久性Cookie, [!DNL Sensor] cs(cookie)(v1st)，該Cookie會在系統內部解譯為x-trackingid。 此永久性Cookie除了設定您的網站可能設定的任何其他Cookie外，也會加以設定。 此Cookie可最佳化您在多個作業期間追蹤訪客的能力，讓您進行許多原本無法進行的分析類型。

[!DNL Sensor] 在Cookie中指派64位元數值金鑰，以識別提出網站要求的新訪客為唯一識別碼。 當瀏 [!DNL Sensor] 覽器看到請求時，會檢查請求資料中是否存在「cs(cookie)(v1st)」(由第一方永久性Cookie設定 [!DNL Sensor])。 如果cs(cookie)(v1st)不存在，則 [!DNL Sensor]透過您的網頁伺服器，會告訴瀏覽器設定。 與其他解決方 [!DNL Sensor] 案不同，您可以在訪客的第一個請求上設定此Cookie。

以下是標準永久性Cookie標題，會在您的網站伺服器第一次要求瀏覽器時，依方向傳送給瀏覽器 [!DNL Sensor]。 如果需要不同的名稱或到期日，可以在配置時定義格式。 例如：

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

此Cookie僅設定一次，即是該訪客對您網站提出的第一個要求。 然後，當瀏覽器在未來每次提出您網站的請求（頁面或內嵌物件請求）時，都會從該訪客收集此資料。 Cookie的大小非常小，可將每次從瀏覽器傳送至網站時，傳送至伺服器的頻寬量降至最低。

接受永久性Cookie由瀏覽器自行決定。 大部分的網頁使用者都瞭解Cookie的功能，並且也瞭解第一方Cookie為他們提供了有價值的好處，讓網站內容可依其偏好自訂。 這些第一方Cookie不會受到常用瀏覽器的預設安全性設定所封鎖。 如果使用者確實選擇封鎖第一方Cookie，其頁面檢視請求仍會記錄，但這些請求的測量資料無法可靠地關聯至網站上的特定訪客或其作業。 許多網站（尤其是複雜的動態網站）都已使用第一方Cookie，這在許多情況下是讓Web應用程式為訪客運作的必要工具。 從永續性Cookie後退的步驟是作業Cookie，可讓一系列請求結合到作業中，但不允許作業間訪客追蹤。 [!DNL Site] 能夠根據工作階段Cookie或IP編號對訪客資料進行作業，但這兩種方法都會明顯降低可與任何其他Web活動分析和報告系統進行之分析的類 [!DNL Site] 型和值。
