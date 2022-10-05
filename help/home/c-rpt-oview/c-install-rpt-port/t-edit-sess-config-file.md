---
description: Report Portal會使用全域.asa設定檔案中的資訊來初始化使用者工作階段。
title: 編輯工作階段組態檔
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# 編輯工作階段組態檔{#edit-the-session-configuration-file}

{{eol}}

Report Portal會使用全域.asa設定檔案中的資訊來初始化使用者工作階段。

安裝時 [!DNL Report Portal]，您必須依指示編輯此檔案。 此 [!DNL global.asa] 檔案位於\*PortalName*\PortalASP\資料夾中。

>[!NOTE]
>
>請勿更改此配置檔案中的任何其他參數。

1. 在運行IIS的電腦上，開啟 [!DNL global.asa] 檔案（如記事本）。
1. 選填。若要讓使用者存取 [!DNL Report Portal] 若沒有驗證，請將Session(&quot;In&quot;)參數值變更為true。 預設值為false，會驗證所有嘗試存取的使用者 [!DNL Report Portal].
1. 若您的 [!DNL Report Portal] 安裝在C驅動器以外的驅動器上，請將Session(&quot;Drive&quot;)參數的值更改為正確的驅動器位置。
1. 對於Session(&quot;DBPath&quot;)參數，更改值以反映包含驗證所需資訊的資料庫路徑 [!DNL Report Portal] 使用者。 請勿包含驅動器號，但務必包含尾斜線。

   範例：[!DNL /Inetpub/wwwroot/Portal/data/]

1. 儲存檔案。
1. 驗證 [!DNL Report Portal] 檔案已正確安裝，且可透過其指定的虛擬目錄存取，請在瀏覽器中開啟下列頁面：

   https://*YourServerAddress*/*YourPortalName*

   範例：[!DNL https://localhost/VisualReportPortal]

   若 [!DNL Report Portal] ASP已正確安裝，您應該會看到入口網站登入頁面。 如果沒有看到此頁，請驗證IIS上是否啟用了ASP，並仔細檢查虛擬目錄映射。
