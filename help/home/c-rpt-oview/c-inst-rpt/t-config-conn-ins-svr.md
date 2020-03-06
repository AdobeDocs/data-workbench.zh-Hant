---
description: 您必須先設定報表伺服器，以指定Insight伺服器的位址，並識別您要其報告的描述檔，才能產生報表和警報。
solution: Analytics
title: 設定與Insight伺服器的連線
topic: Data workbench
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定與Insight伺服器的連線{#configuring-the-connection-to-the-insight-server}

您必須先設定報表伺服器，以指定Insight伺服器的位址，並識別您要報告的描述檔，才能產生報表和警報。

>[!NOTE]
>
>在您依下列說明設定報表伺服器之前，您無法成功執行報表伺服器。 如果您嘗試使用隨程式安裝的未設定檔案來執行報表伺服器，報表伺服器會產生錯誤串流。

**若要設定報表伺服器**

1. 使用Windows檔案總管，導覽至您安裝報表伺服器的目錄。
1. 在記事 [!DNL ReportServer.cfg] 本中開啟檔案，並視需要修改檔案。

   下列範例 [!DNL Report Server.cfg] 依預設僅包含檔案中包含的 [!DNL Report Server.cfg] 參數（並反白顯示所需的參數設定）。 如果您透過代理伺服器與Adobe授權伺服器聯絡，則需要新增授權向量及其參數。 如需詳 [細說明，請參閱Report Server](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) .cfg參數。

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
