---
description: Data Workbench中的「詳細狀態」介面對於疑難排解Data Workbench伺服器和報表伺服器電腦(這些是Data Workbench伺服器的用戶端)的錯誤或其他問題很實用。
title: 顯示報表伺服器狀態
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# 顯示報表伺服器狀態{#displaying-report-server-status}

Data Workbench中的「詳細狀態」介面對於疑難排解Data Workbench伺服器和報表伺服器電腦(這些是Data Workbench伺服器的用戶端)的錯誤或其他問題很實用。

若要在[!DNL Master Server Detailed Status]介面中檢視報表的狀態，您必須將報表狀態伺服器新增至Data Workbench伺服器[!DNL Communications.cfg]檔案中的[!DNL Servers]向量。 以下過程說明如何將報表狀態伺服器添加到[!DNL Communications.cfg]檔案中：

有關[!DNL Detailed Status]介面的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;的管理介面一章。

**新增[!DNL Report Status Server]**

1. 導覽至您安裝Data Workbench伺服器(InsightServer64.exe)的目錄中的「元件」資料夾。

   範例：[!DNL C:\Adobe\Server\Components]
1. 在文本編輯器（如記事本）中開啟[!DNL Communications.cfg]。
1. 找到[!DNL Servers]向量，並將報表狀態伺服器新增至此向量，如下列檔案片段中強調顯示。

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

1. 更新[!DNL Servers]向量的項目計數（即，將項目值增加一），如前一個步驟的檔案片段中強調顯示。
1. 儲存檔案。
