---
description: 若要變更Sensor與之通訊的Data Workbench伺服器（目標伺服器），您必須在安裝Sensor的每個Web伺服器上編輯txlogd.conf檔案。
title: 變更目標 Data Workbench 伺服器
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# 變更目標 Data Workbench 伺服器{#changing-the-target-data-workbench-server}

{{eol}}

若要變更Sensor與之通訊的Data Workbench伺服器（目標伺服器），您必須在安裝Sensor的每個Web伺服器上編輯txlogd.conf檔案。

**要更改為目標[!DNL data workbench server]**

1. 停止原始目標伺服器和新目標伺服器。
1. 複製最新 [!DNL .vsl] 檔案從原始目標伺服器到新目標伺服器。 在稍後的步驟中重新啟動新目標伺服器時，這會導致所有新 [!DNL Sensor] 要附加至目前、現有 [!DNL .vsl] 檔案，而非建立新 [!DNL .vsl] 檔案。 若要這麼做，請完成下列步驟：

   1. 在原始目標伺服器上，瀏覽到 [!DNL \Logs] 檔案夾 [!DNL data workbench server] 安裝目錄。

   1. 複製最新 [!DNL .vsl] 檔案。
   1. 在新目標伺服器上，瀏覽到 [!DNL \Logs] 檔案夾 [!DNL data workbench server] 安裝目錄並貼上 [!DNL .vsl] 檔案到此資料夾。

1. 在其中一台 [!DNL Sensor] 已安裝，請開啟並編輯 [!DNL txlogd.conf] 檔案。 若要這麼做，請完成下列步驟：

   1. 瀏覽至 [!DNL Sensor] 安裝目錄並開啟 [!DNL txlogd.conf] 檔案。

   1. 找出ServerAddress參數並進行更改以反映新目標伺服器的地址。
   1. 儲存並關閉檔案。

1. 在其上的其餘所有Web伺服器上重複步驟2-3 [!DNL Sensor] 已安裝。
1. 重新啟動原始目標伺服器（如果仍要使用）和新目標伺服器。
1. 資料將開始傳輸到您指定的新目標伺服器。
