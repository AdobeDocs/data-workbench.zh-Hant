---
description: 離線或線上使用Data Workbench伺服器的相關資訊。
title: 離線和線上工作
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---

# 離線和線上工作{#working-offline-and-online}

離線或線上使用Data Workbench伺服器的相關資訊。

如果您與[!DNL server]有網路連線，且正線上上運作，Data Workbench會自動從Data Workbench伺服器下載設定檔及其資料的更新。 如果您未指定要聯機工作，Data Workbench會從電腦的快取載入配置檔案及其資料。 在此情況下，您會檢視設定檔的版本，以及上次使用設定檔時下載的資料。

離線工作可提供處理速度優勢，因為您使用本機快取，並在自己的電腦上查詢資料。 線上工作時，每個查詢都必須返回Data Workbench伺服器，這需要更長的時間，並會迫使您與其他線上用戶競爭伺服器資源。 只要您與Data Workbench伺服器有網路連線，離線工作就會阻止Data Workbench伺服器更新Data Workbench上的設定檔或資料，但不會阻止您將項目儲存至Data Workbench伺服器。

由於能夠離線工作，Data Workbench伺服器的大小足以處理資料集中的某些即時流量輸入和某些資料量，以及一些Data Workbench用戶數，但不必調整大小以支援最多的同時用戶數（實際上不常發生）。 由於使用者通常會尋找趨勢和比率，因此您可以隨時探索資料，在大多數情況下，您不需要確切的計數。 如果需要使用目前的資料來查詢和解析確切的計數，您可以線上工作並取得，但查詢需要較長的時間才能解析為100%。

**線上或離線工作**

在側欄中，按一下&#x200B;**[!UICONTROL Connection]**&#x200B;設定，然後按一下&#x200B;**[!UICONTROL Work Online]**。

![](assets/sidebar_work_online.png)

當您聯機工作時，Data Workbench會連線至Data Workbench伺服器，並將您電腦上的資訊與位於Data Workbench伺服器上的設定檔及其資料集資訊同步。

Data Workbench的預設設定是離線工作，但如下節所述，每個使用者可以變更其[!DNL Insight.cfg]檔案，使其Data Workbench例項預設為上線。

**預設聯機工作**

1. 導覽至Insight安裝目錄。
1. 在文字編輯器中開啟[!DNL Insight.cfg]檔案。
1. 將突出顯示的行添加到檔案中，如以下示例所示：

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

下次開啟Data Workbench時，它會連線至Data Workbench伺服器並依預設線上運作。
