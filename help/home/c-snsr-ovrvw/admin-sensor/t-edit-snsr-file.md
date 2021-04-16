---
description: 感測器配置檔案txlogd.conf包含感測器用於建立與資料工作台伺服器連接的參數。
title: 編輯 Sensor txlogd.conf 檔案
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---

# 編輯 Sensor txlogd.conf 檔案{#editing-the-sensor-txlogd-conf-file}

感測器配置檔案txlogd.conf包含感測器用於建立與資料工作台伺服器連接的參數。

這些參數包括伺服器的位址、埠號和通訊協定（HTTP或HTTPS）。 配置檔案還包含日誌內容過濾選項和受控實驗資訊。 受控實驗可讓網站設計人員對所有網站訪客的子集進行實驗，以測試內容或設計變更。

當變更其他[!DNL txlogd.conf]參數（例如[!DNL data workbench server]的IP位址或[!DNL Sensor]的名稱）時，您只需將[!DNL txlogd.conf]取代為更新版本，而[!DNL Sensor]就會自動取代變更。 在某些系統上，如果不停止Web伺服器或發射器進程，則可能無法編輯或替換檔案。

**要開啟和編輯txlogd.conf**

1. 瀏覽至[!DNL Sensor]安裝目錄，並在文字編輯器中開啟[!DNL txlogd.conf]檔案。
1. 視需要編輯檔案。
1. 儲存並關閉檔案。

   * 受控實驗配置檔案（由[!DNL txlogd.conf]檔案中的ExpFile參數定義）的位置應位於Web伺服器上的目錄中，該目錄可供Web內容開發人員訪問或由內容管理系統控制。
   * ExpCookieURL參數中的值是用於測試網站的虛擬頁面。 瀏覽該頁面的使用者會獲得新的追蹤ID。

有關使用[!DNL txlogd.conf]的更多資訊，請聯絡Adobe諮詢服務。
