---
description: 報告入口網站使用名為global.asa的配置檔案中的資訊初始化用戶會話。
solution: Analytics
title: 編輯會話配置檔案
topic: Data workbench
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 編輯會話配置檔案{#edit-the-session-configuration-file}

報告入口網站使用名為global.asa的配置檔案中的資訊初始化用戶會話。

安裝時， [!DNL Report Portal]必須按照指示編輯此檔案。 檔 [!DNL global.asa] 案位於\*PortalName*\PortalASP\ folder。

>[!NOTE]
>
>請勿更改此配置檔案中的任何其他參數。

1. 在運行IIS的電腦上，在文本編輯器( [!DNL global.asa] 如記事本)中開啟檔案。
1. 選填。若要讓使用者不 [!DNL Report Portal] 需驗證即可存取，請將Session(&quot;In&quot;)參數值變更為true。 預設為false，會驗證所有嘗試存取的使用者 [!DNL Report Portal]。
1. 如果您 [!DNL Report Portal] 的C驅動器以外的驅動器安裝了，請將Session(&quot;Drive&quot;)參數的值更改為正確的驅動器位置。
1. 對於Session(&quot;DBPath&quot;)參數，請變更值以反映資料庫的路徑，該路徑包含驗證使用者所需的 [!DNL Report Portal] 資訊。 請勿包含驅動器盤符，但務必包含尾隨斜線。

   範例: [!DNL /Inetpub/wwwroot/Portal/data/]

1. 儲存檔案。
1. 要驗證檔案 [!DNL Report Portal] 是否已正確安裝，並且可以通過指定的虛擬目錄訪問，請在瀏覽器中開啟以下頁：

   http://*YourServerAddress*/*YourPortalName*

   範例: [!DNL http://localhost/VisualReportPortal]

   如果 [!DNL Report Portal] ASP已正確安裝，您應該會看到入口網站登入頁面。 如果您未看到此頁，請驗證IIS上是否啟用了ASP ，並按兩下虛擬目錄映射。

