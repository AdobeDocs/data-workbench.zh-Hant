---
description: 對於所有語言， Report Server 6.0和更新版本都需要複製到Report Server根資料夾的「insight.zbin」檔案。
title: 使用語言檔案 (.zbin 檔案) 更新報表伺服器
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
exl-id: a76b7c01-83f0-4cf2-97a9-07d51cc75b3c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 9%

---

# 使用語言檔案 (.zbin 檔案) 更新報表伺服器{#update-report-server-with-a-language-file-zbin-file}

{{eol}}

對於所有語言， Report Server 6.0和更新版本都需要複製到Report Server根資料夾的「insight.zbin」檔案。

更新報表伺服器語言檔案：

1. 將重新命名的「insight.zbin」檔案新增至根ReportServer目錄。
1. Report Server配置檔案(reportserver.cfg)需要雙位元組語言的字型設定。 例如，中文要求使用SimSun添加字型：

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. 報表伺服器6.0的參數需要傳入命令列才能進行本地化，例如：

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >如果未指定地區，則報表伺服器預設為英文。

   按照步驟以使用Locale參數啟動ReportServer as a服務：

   1. 以管理員身分啟動命令提示。
   1. 導覽至ReportServer安裝資料夾。
   1. 鍵入以下命令以啟動服務：

      * 英語： [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * 中文： [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. 要驗證ReportServer是否使用正確的參數運行，請執行以下操作：

   1. 開啟Windows服務管理器。
   1. 按一下右鍵 [!DNL Adobe Insight Report Server - Properties].

   執行檔的路徑將包含下列參數：

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```
