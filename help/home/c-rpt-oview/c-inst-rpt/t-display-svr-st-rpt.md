---
description: Data Workbench中的「詳細狀態」介面對於疑難排解Data Workbench伺服器和報表伺服器電腦(這些是Data Workbench伺服器的用戶端)的錯誤或其他問題很實用。
title: 顯示報表伺服器狀態
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# 顯示報表伺服器狀態{#displaying-report-server-status}

{{eol}}

Data Workbench中的「詳細狀態」介面對於疑難排解Data Workbench伺服器和報表伺服器電腦(這些是Data Workbench伺服器的用戶端)的錯誤或其他問題很實用。

若要在 [!DNL Master Server Detailed Status] 介面，您必須將報表狀態伺服器新增至 [!DNL Servers] data workbench伺服器中的向量 [!DNL Communications.cfg] 檔案。 以下過程說明如何將報表狀態伺服器添加到 [!DNL Communications.cfg] 檔案：

如需 [!DNL Detailed Status] 介面，請參見 *Data Workbench使用手冊*.

**新增[!DNL Report Status Server]**

1. 導覽至您安裝Data Workbench伺服器(InsightServer64.exe)的目錄中的「元件」資料夾。

   範例：[!DNL C:\Adobe\Server\Components]
1. 開啟 [!DNL Communications.cfg] （例如記事本）。
1. 找出 [!DNL Servers] 向量，並新增報表狀態伺服器至此向量，如下列檔案片段中強調顯示。

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

1. 更新 [!DNL Servers] 向量（即，將項目值增加1），如前一個步驟的檔案片段中強調顯示。
1. 儲存檔案。
