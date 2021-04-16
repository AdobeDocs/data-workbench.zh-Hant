---
description: 報告入口網站使用名為global.asa的配置檔案中的資訊初始化用戶會話。
title: 編輯工作階段組態檔
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# 編輯工作階段組態檔{#edit-the-session-configuration-file}

報告入口網站使用名為global.asa的配置檔案中的資訊初始化用戶會話。

安裝[!DNL Report Portal]時，必須按照指示編輯此檔案。 [!DNL global.asa]檔案位於\*PortalName*\PortalASP\ folder。

>[!NOTE]
>
>請勿更改此配置檔案中的任何其他參數。

1. 在運行IIS的電腦上，在文本編輯器（如記事本）中開啟[!DNL global.asa]檔案。
1. 選填。若要讓使用者不需驗證即可存取[!DNL Report Portal]，請將Session(&quot;In&quot;)參數值變更為true。 預設為false，會驗證所有嘗試存取[!DNL Report Portal]的使用者。
1. 如果[!DNL Report Portal]安裝在C驅動器以外的驅動器上，請將Session(&quot;Drive&quot;)參數的值更改為正確的驅動器位置。
1. 對於Session(&quot;DBPath&quot;)參數，請更改該值以反映資料庫的路徑，該路徑包含驗證[!DNL Report Portal]用戶所需的資訊。 請勿包含驅動器盤符，但務必包含尾隨斜線。

   範例：[!DNL /Inetpub/wwwroot/Portal/data/]

1. 儲存檔案。
1. 要驗證[!DNL Report Portal]檔案是否已正確安裝，並且可以通過其指定的虛擬目錄訪問，請在瀏覽器中開啟以下頁：

   http://*YourServerAddress*/*YourPortalName*

   範例：[!DNL http://localhost/VisualReportPortal]

   如果[!DNL Report Portal] ASP已正確安裝，您應該會看到入口網站登入頁面。 如果您未看到此頁，請驗證IIS上是否啟用了ASP ，並按兩下虛擬目錄映射。
