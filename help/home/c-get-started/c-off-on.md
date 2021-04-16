---
description: 有關離線或聯機使用Data Workbench伺服器的資訊。
title: 離線和線上工作
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---

# 離線和線上工作{#working-offline-and-online}

有關離線或聯機使用Data Workbench伺服器的資訊。

Data Workbench會自動從Data Workbench伺服器下載配置檔案及其資料的更新（如果您與[!DNL server]有網路連接並且正在聯機工作）。 如果您未指定線上上工作，Data Workbench會從您電腦的快取載入描述檔及其資料。 在這種情況下，您正在查看配置檔案的版本及其上次聯機處理配置檔案時下載的資料。

離線工作提供處理速度優勢，因為您正從本機快取工作，並在自己的電腦上查詢資料。 線上工作時，每個查詢都必須返回Data Workbench伺服器，這需要更長的時間，並迫使您與其他線上用戶爭奪伺服器資源。 只要您與Data Workbench伺服器有網路連接，離線工作就會阻止Data Workbench伺服器更新Data Workbench上的配置檔案或資料，但不會阻止您將項目保存到Data Workbench伺服器。

由於能夠離線工作，Data Workbench伺服器的大小可處理資料集中的即時流量輸入和資料量，以及部分Data Workbench使用者，但不需要調整大小以支援最多的同時使用者（實際上並不常發生）。 由於使用者通常會尋找趨勢和比率，因此在您行動時會探索資料，因此在大多數情況下，您不需要確切的計數。 如果需要使用目前的資料來查詢並解析確切的計數，您可以線上上工作並取得，但查詢解析到100%需要更長的時間。

**若要線上或離線工作**

在側欄中，按一下&#x200B;**[!UICONTROL Connection]**&#x200B;設定，然後按一下&#x200B;**[!UICONTROL Work Online]**。

![](assets/sidebar_work_online.png)

當您線上上工作時，Data Workbench會連線至Data Workbench伺服器，並將電腦上的資訊與位於Data Workbench伺服器上的描述檔及其資料集資訊同步。

Data Workbench的預設配置是離線工作，但如下節所述，每個用戶可以更改其[!DNL Insight.cfg]檔案，使其Data Workbench實例預設處於聯機狀態。

**若要依預設線上工作**

1. 導覽至您的Insight安裝目錄。
1. 在文字編輯器中開啟[!DNL Insight.cfg]檔案。
1. 將加亮的行添加到檔案中，如下例所示：

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

下次開啟Data Workbench時，它將連接到Data Workbench伺服器並預設線上。
