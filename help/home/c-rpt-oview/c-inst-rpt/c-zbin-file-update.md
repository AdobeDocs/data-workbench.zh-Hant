---
description: 對於所有語言，Report Server 6.0和更新版本都需要複製到「報表伺服器」根資料夾的「insight.zbin」檔案。
solution: Analytics
title: 使用語言檔案（.zbin檔案）更新報表伺服器
topic: Data workbench
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使用語言檔案（.zbin檔案）更新報表伺服器{#update-report-server-with-a-language-file-zbin-file}

對於所有語言，Report Server 6.0和更新版本都需要複製到「報表伺服器」根資料夾的「insight.zbin」檔案。

更新報表伺服器語言檔案：

1. 將重新命名的「insight.zbin」檔案新增至根ReportServer目錄。
1. 報表伺服器設定檔案(reportserver.cfg)需要雙位元組語言的字型設定。 例如，中文需要使用SimSun添加字型：

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Report Server 6.0的參數必須傳入命令行中，才能進行本地化，例如：

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >如果未指定地區設定，則報表伺服器預設為英文。

   請依照下列步驟，使用地區設定參數啟動ReportServer作為服務：

   1. 以管理員身份啟動命令提示符。
   1. 導覽至ReportServer安裝資料夾。
   1. 鍵入以下命令以啟動服務：

      * 英文版： [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * 中文： [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. 要驗證ReportServer是否使用正確的參數運行：

   1. 開啟Windows Service Manager。
   1. 按一下滑鼠右鍵 [!DNL Adobe Insight Report Server - Properties]。
   執行檔的路徑將包含以下參數：

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

