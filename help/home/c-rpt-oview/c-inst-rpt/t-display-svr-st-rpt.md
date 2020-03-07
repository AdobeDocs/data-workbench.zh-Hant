---
description: 資料工作台中的「詳細狀態」介面對於疑難排解資料工作台伺服器和報表伺服器電腦（資料工作台伺服器的用戶端）的錯誤或其他問題非常有用。
solution: Analytics
title: 顯示報表伺服器狀態
topic: Data workbench
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 顯示報表伺服器狀態{#displaying-report-server-status}

資料工作台中的「詳細狀態」介面對於疑難排解資料工作台伺服器和報表伺服器電腦（資料工作台伺服器的用戶端）的錯誤或其他問題非常有用。

若要在介面中檢視報表狀態， [!DNL Master Server Detailed Status] 您必須在資料工作台伺服器檔案的向量中 [!DNL Servers] 新增報表狀態伺服 [!DNL Communications.cfg] 器。 以下過程介紹如何將報告狀態伺服器添加到文 [!DNL Communications.cfg] 件：

如需介面的詳 [!DNL Detailed Status] 細資訊，請參閱資料工作台使用指南 *的管理介面一章*。

**若要新增[!DNL Report Status Server]**

1. 導覽至您安裝資料工作台伺服器的目錄中的「元件」檔案夾(InsightServer64.exe)。

   範例: [!DNL C:\Adobe\Server\Components]
1. 在文 [!DNL Communications.cfg] 字編輯器（如記事本）中開啟。
1. 找到向 [!DNL Servers] 量並將報表狀態伺服器新增至此向量，如下列檔案片段中反白顯示。

   ```
    . . .
   Servers = vector: 17 items
       0 = FileServer: 
         Local Path = string: Audit\\
         URI = string: /Audit
       1 = FileServer: 
         Local Path = string: Bin\\
         URI = string: /Bin
       2 = FileServer: 
         Local Path = string: Components\\
         URI = string: /Components
     . . .
       16 = ReportStatusServer: 
         URI = string: /ReportStatus.vsp
   ```

1. 更新向量的項 [!DNL Servers] 目計數（即，將項目值增加一），如前一步驟的檔案片段中反白顯示。
1. 儲存檔案。
