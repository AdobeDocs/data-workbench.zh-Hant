---
description: 檢查收集器是否正使用不同方法運行。
title: 確認資料收集器執行中
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# 確認資料收集器執行中{#confirming-that-the-data-collector-is-running}

{{eol}}

檢查收集器是否正使用不同方法運行。

**建議頻率：** 每5-10分鐘

* [在傳送器中使用網站測試功能。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [檢查 [!DNL Sensor] 正在設定Cookie。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## 使用網站測試 {#section-a5a697c3252e40f184c0b662926170f2}

驗證收集器是否正在運行的一種方法是在發射器中啟用站點測試功能。 啟用站點測試時，發射器會定期（每60秒）向運行收集器的Web伺服器發送GET請求。 如果站點測試未從Web伺服器獲取響應，則它將錯誤消息寫入syslog，並將錯誤消息發送到 [!DNL data workbench server] （寫入感測器日誌檔案）。

如果站點測試收到來自Web伺服器的響應，則在隊列檔案中查找來自Web伺服器的資料包。 如果資料包未出現（表示收集器未運行以捕獲事件），則站點測試將錯誤消息寫入syslog並向Adobe發送錯誤消息（也寫入感測器日誌檔案）。

在Site Test發送給Web伺服器的請求中， Site Test將User-Agent值設定為「 [!DNL Sensor] 測試。」 如果您不希望這些請求出現在資料集中，請新增「 [!DNL Sensor] 測試「使用者代理」至 [!DNL Baseline Robots List.txt] 檔案或 [!DNL Extended Robots List.txt] 檔案 [!DNL Lookups] 資料夾 [!DNL data workbench server].

**在傳輸器中啟用站點測試**

1. 找出 [!DNL txlogd.conf] 檔案 [!DNL Sensor] 執行中，並在文字編輯器中開啟它。

1. 在 [!DNL txlogd.conf] ，找出「SiteTest」行並進行設定，如下所示。 若您的 [!DNL txlogd.conf] 檔案中不包含「SiteTest」行，只需將該行新增至設定檔案的結尾即可。

   SiteTest http, *serverAddress*, *埠*, *資源*

   where *serverAddress* 是Web伺服器的名稱或IP地址， *埠* 是伺服器的HTTP監聽埠， *資源* 是您要網站測試在測試伺服器時要求的特定資源。 請注意 *資源* 可包含查詢字串。

   範例：SiteTest http,localhost,80,/index.jsp

   要測試多個Web伺服器，只需指定多條SiteTest線路。

## 檢查Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

驗證收集器是否在Web伺服器上運行的另一種方法是檢查 [!DNL Sensor] 會在回應中設定Web伺服器傳回給用戶端的Cookie。 如果收集器運作中，Web伺服器會傳回「v1st」Cookie。

您可以重新命名Cookie。 如果您已這麼做，則必須尋找指定的名稱，而非v1st。

您可以使用自動指令碼或監視代理執行此檢查。 如需此工作的範例指令碼或其他說明，請連絡Adobe諮詢服務。
