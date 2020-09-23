---
description: 要更改感測器與之通信的資料工作台伺服器（目標伺服器），必須在安裝感測器的每個Web伺服器上編輯txlogd.conf檔案。
solution: Analytics
title: 變更目標 Data Workbench 伺服器
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---


# 變更目標 Data Workbench 伺服器{#changing-the-target-data-workbench-server}

要更改感測器與之通信的資料工作台伺服器（目標伺服器），必須在安裝感測器的每個Web伺服器上編輯txlogd.conf檔案。

**若要變更為目標[!DNL data workbench server]**

1. 同時停止原始目標伺服器和新目標伺服器。
1. 將最新檔案從 [!DNL .vsl] 原始目標伺服器複製到新目標伺服器。 在稍後的步驟中重新啟動新目標伺服器時，這會將所有新 [!DNL Sensor] 資料附加到當前的現有 [!DNL .vsl] 檔案，而不是建立新文 [!DNL .vsl] 件。 若要這麼做，請完成下列步驟：

   1. 在原始目標伺服器上，瀏覽到安 [!DNL \Logs] 裝目錄中的 [!DNL data workbench server] 資料夾。

   1. 複製資料夾中 [!DNL .vsl] 最新的檔案。
   1. 在新目標伺服器上，瀏覽到安裝目 [!DNL \Logs] 錄中的檔案 [!DNL data workbench server] 夾，然後將檔案 [!DNL .vsl] 貼上到此資料夾。

1. 在其中一個安裝的Web服 [!DNL Sensor] 務器上，開啟和編輯文 [!DNL txlogd.conf] 件。 若要這麼做，請完成下列步驟：

   1. 瀏覽至安 [!DNL Sensor] 裝目錄，並在文字 [!DNL txlogd.conf] 編輯器中開啟檔案。

   1. 找到ServerAddress參數並加以變更，以反映新目標伺服器的地址。
   1. 儲存並關閉檔案。

1. 對安裝的其餘所有Web伺服器重複步驟2 [!DNL Sensor] -3。
1. 重新啟動原始目標伺服器（如果仍要使用）和新目標伺服器。
1. 資料將開始傳輸至您指定的新目標伺服器。
