---
description: 檢查收集器是否使用不同的方法運行。
solution: Analytics
title: 確認資料收集器執行中
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---


# 確認資料收集器執行中{#confirming-that-the-data-collector-is-running}

檢查收集器是否使用不同的方法運行。

**建議頻率：** 每5-10分鐘

* [在發射器中使用「網站測試功能」。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [檢查 [!DNL Sensor] 是否設定Cookie。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## 使用網站測試 {#section-a5a697c3252e40f184c0b662926170f2}

驗證收集器是否正在運行的一種方法是在發射器中啟用「站點測試」功能。 啟用站點測試時，發射器會定期（每60秒）向運行收集器的Web伺服器發送GET請求。 如果站點測試未從Web伺服器獲得響應，它將錯誤消息寫入syslog並向 [!DNL data workbench server] （寫入感測器日誌檔案）發送錯誤消息。

如果網站測試收到來自網站伺服器的回應，它會在佇列檔案中尋找來自網站伺服器的封包。 如果資料包未出現（表示收集器未運行以捕獲事件）,Site Test會向syslog寫入錯誤消息，並向Adobe發送錯誤消息（也會寫入感測器日誌檔案）。

在「網站測試」傳送至網站伺服器的請求中，「網站測試」會將「使用者代理」值設定為「 [!DNL Sensor] 測試」。 如果您不希望這些請求出現在資料集中，請將「 [!DNL Sensor] Test」 User-Agent新增至檔案或資料夾 [!DNL Baseline Robots List.txt] 中的檔案 [!DNL Extended Robots List.txt][!DNL Lookups][!DNL data workbench server]。

**在發射器中啟用站點測試**

1. 在執行 [!DNL txlogd.conf] 中的機器上找到檔 [!DNL Sensor] 案，並在文字編輯器中開啟它。

1. 在檔 [!DNL txlogd.conf] 案中，找到「SiteTest」行並設定，如下所示。 如果您 [!DNL txlogd.conf] 的檔案不包含「SiteTest」行，只需將該行新增至設定檔案的結尾。

   SiteTest http, *serverAddress*, *port*, resource **

   其中 *serverAddress* 是Web伺服器的名稱或IP位址，port *是伺服器的HTTP監聽埠，*** resource是您在測試伺服器時希望Site Test要求的特定資源。 請注意 *，資源* 可包含查詢字串。

   範例：SiteTest http,localhost,80,/index.jsp

   若要測試多個Web伺服器，您只需指定多個SiteTest行。

## 檢查Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

另一個驗證收集器是否在Web伺服器上運行的方法是檢查 [!DNL Sensor] Web伺服器是否在返回客戶端的響應中設定Cookie。 如果收集器正在運作，Web伺服器會傳回「v1st」Cookie。

您可以重新命名Cookie。 如果您已這麼做，則必須尋找指定的名稱，而非v1st。

您可以使用自動指令碼或監視代理執行此檢查。 如需此工作的範例指令碼或其他說明，請聯絡Adobe諮詢服務。
