---
description: Report Portal會使用全域.asa設定檔案中的資訊來初始化使用者工作階段。
title: 編輯工作階段組態檔
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# 編輯工作階段組態檔{#edit-the-session-configuration-file}

Report Portal會使用全域.asa設定檔案中的資訊來初始化使用者工作階段。

安裝[!DNL Report Portal]時，必須按照指示編輯此檔案。 [!DNL global.asa]檔案位於\*PortalName*\PortalASP\ folder中。

>[!NOTE]
>
>請勿更改此配置檔案中的任何其他參數。

1. 在運行IIS的電腦上，在文本編輯器（如記事本）中開啟[!DNL global.asa]檔案。
1. 選填。若要讓使用者在不進行驗證的情況下存取[!DNL Report Portal]，請將Session(&quot;In&quot;)參數值變更為true。 預設值為false，驗證所有嘗試訪問[!DNL Report Portal]的用戶。
1. 如果[!DNL Report Portal]安裝在C驅動器以外的驅動器上，請將Session(&quot;Drive&quot;)參數的值更改為正確的驅動器位置。
1. 對於Session(&quot;DBPath&quot;)參數，更改值以反映資料庫的路徑，該路徑包含驗證[!DNL Report Portal]用戶所需的資訊。 請勿包含驅動器號，但務必包含尾斜線。

   範例：[!DNL /Inetpub/wwwroot/Portal/data/]

1. 儲存檔案。
1. 要驗證[!DNL Report Portal]檔案是否已正確安裝，並且可通過其指定的虛擬目錄訪問，請在瀏覽器中開啟以下頁：

   http://*YourServerAddress*/*YourPortalName*

   範例：[!DNL http://localhost/VisualReportPortal]

   如果[!DNL Report Portal] ASP已正確安裝，您應該會看到入口登錄頁。 如果沒有看到此頁，請驗證IIS上是否啟用了ASP，並仔細檢查虛擬目錄映射。
