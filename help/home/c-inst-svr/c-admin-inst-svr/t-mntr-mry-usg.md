---
description: 有關評估和監控地址空間負載的資訊。
title: 監控記憶體使用情況
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
exl-id: b8c0b33b-dbec-4947-911b-11c8a83bbc9c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---

# 監控記憶體使用情況{#monitoring-memory-usage}

有關評估和監控地址空間負載的資訊。

**監視地址空間負載**

**建議頻率：** 每日

地址空間負載是對正確配置[!DNL Insight Server]使用的最大地址空間百分比的度量。 即使配置參數被更改以減少記憶體使用量，它通常在[!DNL Insight Server]服務重新啟動之前不會減少。

地址空間負載最大值中內置了安全裕量，以說明地址空間利用率的意外增加。 你絕不應該故意割傷這個安全區。 它存在於緊急情況，而不是支援您的Adobe應用程式新增的功能。

>[!NOTE]
>
>要使更多地址空間可用並避免記憶體耗盡錯誤，請確保您的作業系統已啟用/3GB交換機，並且低碎片堆正在運行。

記錄到[!DNL Insight Server]事件資料日誌的錯誤可提供線索，說明問題正隨著地址空間負載而發展：

* 「請求的X位元組塊太大」錯誤表明某些錯誤可能對地址空間負載、效能和網路頻寬造成過大影響。 這樣大的塊可以極大地增加地址空間的使用，這既需要大量記憶體，又需要大的地址空間連續塊。

   要解決此問題，您可以減少最大維度的基數，進而增加地址空間負載。 如果無法減少維的基數，則應嘗試將「地址空間」載入保持得足夠小，以便您可以處理意外的增加。
* 「超出記憶體預算」錯誤表示您可能需要增加查詢記憶體限制。 查詢使用的記憶體與維基數成比例，在某些情況下，還與元素名稱的長度成比例。 如果增加「查詢記憶體限制」，則會增加總地址空間負載並縮小大尺寸。

>[!NOTE]
>
>預設情況下，允許使用大頁，並禁用記憶體映射查找。 在DWB 6.7和更新版本中，可在資料集設定中變更此項目。 任何更改都需要重新啟動伺服器。

**評估地址空間負載**

為了準確評估系統的「地址空間」負載，Adobe建議重新處理資料集，執行一些普通查詢，而不隨後重新啟動[!DNL Insight Server]，然後按照這些步驟查看測量的「地址空間」負載。

如果自上次重新啟動以來未重新處理和查詢[!DNL Insight Server]，則不應從「地址空間」負載得出結論。

1. 在[!DNL Insight]中，在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵要配置的[!DNL Insight Server]表徵圖，然後按一下&#x200B;**[!UICONTROL Detailed Status]**。
1. 在「詳細狀態」介面中，按一下&#x200B;**[!UICONTROL Memory Status]**&#x200B;查看其內容。 在「地址空間載入」參數中，您可以看到以百分比表示的「地址空間」載入，以及用括弧表示狀態的說明。

   下表顯示「地址空間」負載的範圍和狀態。 會針對每個範圍列出建議的動作。

   | 地址空間負載(%) | 狀態 | 建議的動作 |
   |---|---|---|
   | 0-15 | 瘦弱而平庸 | 無. |
   | 15-33 | 光 | 無. |
   | 33-66 | 審核 | 無. |
   | 66-100 | 重 | 為避免記憶體耗盡故障，請勿添加大量額外功能或嘗試處理更多資料。 |
   | 100-125 | 可靠性損失 | 調整資料集組態以減少「位址空間」負載。 |
   | 125或更高 | 臨近 | 調整資料集組態以減少「位址空間」負載。 在發生故障之前，您可能看不到故障即將發生的狀態。 |

   如果您看到「地址空間」負載超過100%，則應盡快更改配置，以減少「地址空間」的使用。
