---
description: 檢查收集器是否使用不同的方法運行。
title: 確認資料收集器執行中
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# 確認資料收集器執行中{#confirming-that-the-data-collector-is-running}

檢查收集器是否使用不同的方法運行。

**建議頻率：** 每5-10分鐘

* [在發射器中使用「網站測試功能」。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [檢查 [!DNL Sensor] 是否設定Cookie。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## 使用站點測試{#section-a5a697c3252e40f184c0b662926170f2}

驗證收集器是否正在運行的一種方法是在發射器中啟用「站點測試」功能。 啟用「站點測試」時，發射器會定期（每60秒）向運行收集器的Web伺服器發送GET請求。 如果站點測試未從Web伺服器獲得響應，它將錯誤消息寫入syslog並向[!DNL data workbench server]發送錯誤消息（寫入感測器日誌檔案）。

如果網站測試收到來自網站伺服器的回應，它會在佇列檔案中尋找來自網站伺服器的封包。 如果資料包未出現（表示收集器未運行以捕獲事件）,Site Test將錯誤消息寫入syslog並向Adobe發送錯誤消息（也將寫入感測器日誌檔案）。

在網站測試傳送至網站伺服器的請求中，網站測試會將使用者代理值設為「[!DNL Sensor]測試」。 如果您不希望這些請求出現在您的資料集中，請將「[!DNL Sensor]測試」User-Agent新增至[!DNL Baseline Robots List.txt]檔案，或將[!DNL Lookups]檔案夾中的[!DNL Extended Robots List.txt]檔案新增至[!DNL data workbench server]。

**在發射器中啟用站點測試**

1. 在運行[!DNL Sensor]的電腦上找到[!DNL txlogd.conf]檔案，並在文本編輯器中將其開啟。

1. 在[!DNL txlogd.conf]檔案中，找到&quot;SiteTest&quot;行並設定它，如下所示。 如果您的[!DNL txlogd.conf]檔案不包含&quot;SiteTest&quot;行，只需將該行新增至設定檔案的結尾。

   SiteTest http, *serverAddress*, *port*, *resource*

   其中&#x200B;*serverAddress*&#x200B;是Web伺服器的名稱或IP位址，*port*&#x200B;是伺服器的HTTP監聽埠，而&#x200B;*resource*&#x200B;是您在測試伺服器時希望網站測試要求的特定資源。 請注意，*resource*&#x200B;可以包含查詢字串。

   範例：SiteTest http,localhost,80,/index.jsp

   若要測試多個Web伺服器，您只需指定多個SiteTest行。

## 正在檢查Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

另一種驗證收集器是否在Web伺服器上運行的方法是檢查[!DNL Sensor]是否在Web伺服器返回客戶端的響應中設定Cookie。 如果收集器正在運作，Web伺服器會傳回「v1st」Cookie。

您可以重新命名Cookie。 如果您已這麼做，則必須尋找指定的名稱，而非v1st。

您可以使用自動指令碼或監視代理執行此檢查。 如需此工作的範例指令碼或其他說明，請聯絡Adobe諮詢服務。
