---
description: 要更徹底地監視實施，您可以監視伺服器電腦上的所有埠以及每個埠上運行的軟體產品。
title: 監控連接埠和應用程式
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
exl-id: 418b2e5c-42ec-40f0-9cae-375194288143
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---

# 監控連接埠和應用程式{#monitoring-ports-and-applications}

要更徹底地監視實施，您可以監視伺服器電腦上的所有埠以及每個埠上運行的軟體產品。

**建議頻率：** 每5-10分鐘

使用應用程式或指令碼，可以監視每個應用程式運行的TCP埠（通常為埠80或443），以確保應用程式綁定到該埠。 要執行此操作，請從要監視的電腦請求應用程式狀態頁。

**請求應用程式狀態頁**

1. 在要監視的電腦上，修改訪問控制，以允許監視應用程式或指令碼訪問電腦。 有關說明，請參閱[配置訪問控制](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)。
1. 連接到[!DNL https://IP Address/Status/]，其中IP地址是要接收狀態的電腦的IP地址。

   範例：[!DNL https://127.0.0.1/Status/]

   電腦應以伺服器狀態說明作出回應。 如果未回應，請檢查您的事件記錄，並聯絡Adobe客戶服務。

   如需此類進階監控的詳細資訊，請連絡Adobe諮詢服務。
