---
description: Sensor設定檔案txlogd.conf包含Sensor用來建立與Data Workbench伺服器連線的參數。
title: 編輯 Sensor txlogd.conf 檔案
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---

# 編輯 Sensor txlogd.conf 檔案{#editing-the-sensor-txlogd-conf-file}

Sensor設定檔案txlogd.conf包含Sensor用來建立與Data Workbench伺服器連線的參數。

這些參數包括伺服器的地址、埠號和通信協定（HTTP或HTTPS）。 配置檔案還包含日誌內容過濾選項和受控實驗資訊。 受控實驗可讓網站設計人員執行實驗，以測試內容或設計所有網站訪客子集的變更。

更改其他[!DNL txlogd.conf]參數時，例如[!DNL data workbench server]的IP地址或[!DNL Sensor]的名稱時，您可以直接用更新的版本替換[!DNL txlogd.conf]，而[!DNL Sensor]將自動獲取更改。 在某些系統上，如果不停止Web伺服器或傳輸器進程，您可能無法編輯或替換檔案。

**若要開啟和編輯txlogd.conf**

1. 瀏覽至[!DNL Sensor]安裝目錄，並在文字編輯器中開啟[!DNL txlogd.conf]檔案。
1. 視需要編輯檔案。
1. 儲存並關閉檔案。

   * 受控實驗配置檔案的位置（由[!DNL txlogd.conf]檔案中的ExpFile參數定義）應位於Web伺服器上可供Web內容開發人員訪問或由內容管理系統控制的目錄中。
   * ExpCookieURL參數中的值是用來測試網站的虛擬頁面。 造訪該頁面的使用者會獲得新的追蹤ID。

有關使用[!DNL txlogd.conf]的詳細資訊，請聯繫Adobe咨詢服務。
