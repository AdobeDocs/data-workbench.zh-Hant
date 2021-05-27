---
description: 若要連線至Data Workbench伺服器，報表伺服器必須擁有存取該伺服器的權限。
title: 啟用 Data Workbench 伺服器的存取權
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# 啟用 Data Workbench 伺服器的存取權{#enabling-access-to-the-data-workbench-server}

若要連線至Data Workbench伺服器，報表伺服器必須擁有存取該伺服器的權限。

您可以將報表伺服器的通用名稱（如報表伺服器的數位憑證上指派）新增至伺服器的存取控制檔案，以授與Data Workbench伺服器的存取權。

>[!NOTE]
>
>在叢集環境中工作時，應將報表伺服器設定為存取主資料工作台伺服器，以避免同步問題。 在Data Workbench中，您可以使用[!DNL Servers Manager]中的[!DNL Related Servers]功能表項目，檢視叢集中處理伺服器的相關資訊。 有關[!DNL Servers Manager]的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;的管理介面一章。

以下程式說明如何手動將報表伺服器新增至Data Workbench伺服器上的存取控制檔案。 若要以此方式更新存取控制檔案，您必須在安裝Data Workbench伺服器的電腦上擁有檔案系統存取權。

您也可以使用Data Workbench中的[!DNL Server Files Manager]更新伺服器的存取控制檔案。 若要這麼做，您的Data Workbench用戶端必須具有伺服器的管理權限。

有關[!DNL Server Files Manager]的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;的管理介面一章。

**設定Data Workbench伺服器的存取權**

1. 導覽至您安裝Data Workbench伺服器(InsightServer64.exe)的目錄中的「存取控制」資料夾。

   範例：[!DNL C:\Adobe\Server\Access Control]

1. 在文本編輯器（如記事本）中開啟[!DNL Access Control.cfg]。
1. 找到[!DNL Report Server AccessGroup] ，並將[!DNL Report Server’s]公用名稱添加到此組，如以下檔案片段中突出顯示的。 （鍵入與[!DNL Report Server’s]數字證書上完全相同的通用名稱。）

   ```
   . . .
     5 = AccessGroup: 
       Members = vector: 1 items
         0 = string: CN: ReportCommonName
       Name = string: Report Server
       Read-Only Access = vector: 5 items
         0 = string: /Profiles/$
         1 = string: /Status/
         3 = string: /Software/
         4 = string: /Addresses/
         5 = string: /Users/$
       Read-Write Access = vector: 3 items
         0 = string: /Profiles/
         1 = string: /Users/%CN%/
         2 = string: /ReportStatus.vsp
      . . .
   ```

1. 儲存檔案。
