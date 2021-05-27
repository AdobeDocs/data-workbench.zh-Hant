---
description: 檢查收集器是否正使用不同方法運行。
title: 確認資料收集器執行中
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# 確認資料收集器執行中{#confirming-that-the-data-collector-is-running}

檢查收集器是否正使用不同方法運行。

**建議頻率：** 每5-10分鐘

* [在傳送器中使用網站測試功能。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [檢查 [!DNL Sensor] 是否設定Cookie。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## 使用站點測試{#section-a5a697c3252e40f184c0b662926170f2}

驗證收集器是否正在運行的一種方法是在發射器中啟用站點測試功能。 啟用站點測試時，發射器會定期（每60秒）向運行收集器的Web伺服器發送GET請求。 如果站點測試未從Web伺服器獲取響應，它將錯誤消息寫入syslog並向[!DNL data workbench server]發送錯誤消息（寫入感測器日誌檔案）。

如果站點測試收到來自Web伺服器的響應，則在隊列檔案中查找來自Web伺服器的資料包。 如果資料包未出現（表示收集器未運行以捕獲事件），則站點測試將錯誤消息寫入syslog並向Adobe發送錯誤消息（也寫入感測器日誌檔案）。

在站點測試發送到Web伺服器的請求中，站點測試將User-Agent值設定為&quot; [!DNL Sensor] Test&quot;。 如果您不希望這些請求在資料集中顯示，請將「 [!DNL Sensor] Test」 User-Agent添加到[!DNL Baseline Robots List.txt]檔案或[!DNL data workbench server]資料夾的[!DNL Lookups]檔案中。[!DNL Extended Robots List.txt]

**在傳輸器中啟用站點測試**

1. 在運行[!DNL Sensor]的電腦上找到[!DNL txlogd.conf]檔案，並在文本編輯器中開啟它。

1. 在[!DNL txlogd.conf]檔案中，找出「SiteTest」行並進行設定，如下所示。 如果您的[!DNL txlogd.conf]檔案不包含「SiteTest」行，只需將該行添加到配置檔案的結尾即可。

   SiteTest http, *serverAddress*, *port*, *resource*

   其中&#x200B;*serverAddress*&#x200B;是Web伺服器的名稱或IP地址，*port*&#x200B;是伺服器的HTTP偵聽埠，而&#x200B;*resource*&#x200B;是在測試伺服器時希望站點測試請求的特定資源。 請注意，*resource*&#x200B;可包含查詢字串。

   範例：SiteTest http,localhost,80,/index.jsp

   要測試多個Web伺服器，只需指定多條SiteTest線路。

## 檢查Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

驗證收集器是否在Web伺服器上運行的另一種方法是檢查[!DNL Sensor]是否在Web伺服器返回給客戶端的響應中設定Cookie。 如果收集器運作中，Web伺服器會傳回「v1st」Cookie。

您可以重新命名Cookie。 如果您已這麼做，則必須尋找指定的名稱，而非v1st。

您可以使用自動指令碼或監視代理執行此檢查。 如需此工作的範例指令碼或其他說明，請連絡Adobe諮詢服務。
