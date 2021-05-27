---
description: 若要變更Sensor與之通訊的Data Workbench伺服器（目標伺服器），您必須在安裝Sensor的每個Web伺服器上編輯txlogd.conf檔案。
title: 變更目標 Data Workbench 伺服器
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# 變更目標 Data Workbench 伺服器{#changing-the-target-data-workbench-server}

若要變更Sensor與之通訊的Data Workbench伺服器（目標伺服器），您必須在安裝Sensor的每個Web伺服器上編輯txlogd.conf檔案。

**要更改為目標[!DNL data workbench server]**

1. 停止原始目標伺服器和新目標伺服器。
1. 將最新的[!DNL .vsl]檔案從原始目標伺服器複製到新目標伺服器。 在後續步驟中重新啟動新目標伺服器時，這會導致所有新[!DNL Sensor]資料附加到當前的現有[!DNL .vsl]檔案，而不是建立新的[!DNL .vsl]檔案。 若要這麼做，請完成下列步驟：

   1. 在原始目標伺服器上，瀏覽[!DNL data workbench server]安裝目錄中的[!DNL \Logs]資料夾。

   1. 複製資料夾中最新的[!DNL .vsl]檔案。
   1. 在新目標伺服器上，瀏覽到[!DNL data workbench server]安裝目錄中的[!DNL \Logs]資料夾，然後將[!DNL .vsl]檔案貼到此資料夾。

1. 在安裝[!DNL Sensor]的其中一台Web伺服器上，開啟並編輯[!DNL txlogd.conf]檔案。 若要這麼做，請完成下列步驟：

   1. 瀏覽至[!DNL Sensor]安裝目錄，並在文字編輯器中開啟[!DNL txlogd.conf]檔案。

   1. 找出ServerAddress參數並進行更改以反映新目標伺服器的地址。
   1. 儲存並關閉檔案。

1. 在已安裝[!DNL Sensor]的其餘所有Web伺服器上重複步驟2-3。
1. 重新啟動原始目標伺服器（如果仍要使用）和新目標伺服器。
1. 資料將開始傳輸到您指定的新目標伺服器。
