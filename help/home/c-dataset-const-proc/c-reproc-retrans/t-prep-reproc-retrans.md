---
description: 確保重新處理或重新轉換工作順利進行並及時完成的步驟，讓資料工作台使用者可以返回工作
solution: Analytics
title: 準備重新處理或重新轉換
topic: Data workbench
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 準備重新處理或重新轉換{#preparing-for-reprocessing-or-retransformation}

確保重新處理或重新轉換工作順利進行並及時完成的步驟，讓資料工作台使用者可以返回工作

1. 在介面中檢查資料集描述檔，以判斷先前處理或轉換的 [!DNL Processing Mode History] 經過 [!DNL Detailed Status] 時間。

   1. 在資料集設定檔中工作時，請開啟介 [!DNL Detailed Status] 面。
   1. 按一 **[!UICONTROL Processing Status]** 下> *&lt;**[!UICONTROL dataset profile name]**>***[!UICONTROL Processing Mode History]** >以檢視先前處理或轉換的經過時間。

      * 「快速輸入」是記錄處理所需的總時間。
      * 「快速合併」是轉換所需的總時間。
      * 兩次（快速輸入+快速合併）的總和是處理資料集所需的總時間。
      以下範例指出記錄處理大約需要43秒，而轉換則需要不到2分鐘。

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      如需介面的詳細資 [!DNL Detailed Status] 訊，請參閱資 *料工作台使用指南*。


1. 排程並規劃重新處理。 由於資料工作台使用者在記錄處理階段無法存取資料，請確定您排程在適當的時間（例如週末）進行重新處理。
1. 使用「有關的詳細資訊，請參閱資料工作台使用手冊」中的 [!DNL Processing Legend.] 欄位，監視重新處理 [!DNL Processing Legend]和重 *新轉換的進度*。
