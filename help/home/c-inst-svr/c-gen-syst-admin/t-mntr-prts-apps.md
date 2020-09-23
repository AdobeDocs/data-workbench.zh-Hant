---
description: 要更徹底地監控實施，您可以監控伺服器電腦上的所有埠以及這些埠上運行的軟體產品。
solution: Analytics
title: 監控連接埠和應用程式
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---


# 監控連接埠和應用程式{#monitoring-ports-and-applications}

要更徹底地監控實施，您可以監控伺服器電腦上的所有埠以及這些埠上運行的軟體產品。

**建議頻率：** 每5-10分鐘

使用應用程式或指令碼，可以監視每個應用程式在其上運行的TCP埠（通常是埠80或443），以確保應用程式綁定到該埠。 若要這麼做，請向您要監視的電腦要求應用程式狀態頁面。

**要請求應用程式狀態頁**

1. 在要監視的電腦上，修改訪問控制以允許監視應用程式或指令碼訪問電腦。 有關說明，請參 [閱配置訪問控制](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)。
1. 連接 [!DNL https://IP Address/Status/]到，其中IP地址是要接收其狀態的電腦的IP地址。

   範例：[!DNL https://127.0.0.1/Status/]

   電腦應以伺服器狀態說明作出響應。 如果未回應，請檢查您的事件記錄並聯絡Adobe客戶服務。

   如需此類進階監控的詳細資訊，請聯絡Adobe諮詢服務。

