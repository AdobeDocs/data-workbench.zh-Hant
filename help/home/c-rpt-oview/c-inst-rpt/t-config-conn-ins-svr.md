---
description: 您必須設定報表伺服器以指定Insight Server的位址，並識別您要其報告的設定檔，才能產生報表和警報。
title: 設定與 Insight Server 的連線
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
exl-id: a398a665-fe09-448a-977c-b0f9de4add09
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# 設定與 Insight Server 的連線{#configuring-the-connection-to-the-insight-server}

您必須設定報表伺服器以指定Insight Server的位址，並識別您要其報告的設定檔，才能產生報表和警報。

>[!NOTE]
>
>在您依下列說明設定報表伺服器之前，您無法成功執行報表伺服器。 如果您嘗試使用程式中安裝的未配置檔案來運行報表伺服器，則報表伺服器會生成錯誤流。

**設定報表伺服器**

1. 使用Windows資源管理器，導航至安裝Report Server的目錄。
1. 在記事本中開啟[!DNL ReportServer.cfg]檔案，並視需要修改檔案。

   下列範例[!DNL Report Server.cfg]依預設僅包含[!DNL Report Server.cfg]檔案中包含的參數（並反白顯示所需的參數設定）。 如果您透過代理伺服器與Adobe授權伺服器連絡，則需要新增授權向量及其參數。 如需詳細說明，請參閱[Report Server.cfg參數](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) 。

   ```
   Fonts = vector: 0 items
   Gamma = float: 1.6
   Network Location = string: NetworkLocationName
   Servers = vector: 1 items
     0 = serverInfo:
       Address = string: ServerIPAddress
       Name = string: 
       Port = int: 443
       Proxy Address = string:
       Proxy Password = string:
       Proxy Port = int: 8080
       Proxy User Name = string:
       SSL Client Certificate = string: ReportCertFileName.pem
       SSL Server Common Name = string: ServerCommonName
       Use SSL = bool: true
   Result Memory Limit (KB) = double: 100000
   Maximum Slice Size = int: 30
   Use OpenGL Hardware Rendering = bool: true
   Reporting = :
     Profiles = vector: 1 items
       0 = ReportProfile:
         Server = string: ServerCommonName
         Profile = string: ProfileName
     Update Interval (minutes) = int: 10
     Completion Message Interval (seconds) = int: 600
     Status interval (seconds) = int: 600
     SMTP Server for Errors = string: SMTPServerHostName
     SMTP Server for Errors Username = string: SMTPServerUsername
     SMTP Server for Errors Password = string: SMTPServerPassword
     SMTP Server for Errors Send From = string: SenderAddress
     SMTP Server for Errors Send To = string: RecipientAddresses
   ```

1. 儲存並關閉檔案。
