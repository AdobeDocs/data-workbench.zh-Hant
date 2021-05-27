---
description: 確保重新處理或重新轉換順暢進行，並及時完成，讓Data Workbench使用者可返回工作
title: 準備重新處理或重新轉換
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 4%

---

# 準備重新處理或重新轉換{#preparing-for-reprocessing-or-retransformation}

確保重新處理或重新轉換順暢進行，並及時完成，讓Data Workbench使用者可返回工作

1. 在[!DNL Detailed Status]介面中檢查資料集設定檔的[!DNL Processing Mode History]，以決定先前處理或轉換的經過時間。

   1. 在資料集設定檔中工作時，請開啟[!DNL Detailed Status]介面。
   1. 按一下「**[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]**」以檢視先前處理或轉換的經過時間。

      * 「快速輸入」是記錄處理所需的總時間。
      * 「快速合併」是轉換所需的總時間。
      * 兩次的總和（快速輸入+快速合併）是處理資料集所需的總時間。

      以下範例指出記錄處理約需43秒，轉換則需不到2分鐘。

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      有關[!DNL Detailed Status]介面的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*。


1. 排程並規劃重新處理。 由於Data Workbench使用者在記錄處理階段期間無法存取資料，請確定您排程在適當時間（例如週末）重新處理。
1. 使用[!DNL Processing Legend.]中的欄位監控重新處理和重新轉換的進度有關[!DNL Processing Legend]的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*。
