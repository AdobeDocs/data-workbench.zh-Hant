---
description: 若要連線至資料工作台伺服器，報表伺服器必須擁有存取該伺服器的權限。
solution: Analytics
title: 啟用資料工作台伺服器的存取權
topic: Data workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 啟用資料工作台伺服器的存取權{#enabling-access-to-the-data-workbench-server}

若要連線至資料工作台伺服器，報表伺服器必須擁有存取該伺服器的權限。

您可將報表伺服器的公用名稱（如報表伺服器的數位憑證所指派）新增至伺服器的存取控制檔案，以授與資料工作台伺服器的存取權。

>[!NOTE]
>
>在叢集環境中工作時，應將報表伺服器設定為存取主資料工作台伺服器，以避免同步問題。 在資料工作台中，您可以使用中的功能表項目，檢視有關處理叢集 [!DNL Related Servers] 中伺服器的資訊 [!DNL Servers Manager]。 如需有關的詳細資 [!DNL Servers Manager]訊，請參閱資料工作台使用指南的「管 *理介面」一章*。

下列程式說明如何手動將報表伺服器新增至資料工作台伺服器上的存取控制檔案。 要以這種方式更新訪問控制檔案，必須在安裝資料工作台伺服器的電腦上具有檔案系統訪問權限。

您也可以使用資料工作台中的更新伺服器的存 [!DNL Server Files Manager] 取控制檔案。 若要這麼做，您的資料工作台用戶端必須具有伺服器的管理權限。

如需有關的詳細資 [!DNL Server Files Manager]訊，請參閱資料工作台使用指南的「管 *理介面」一章*。

**若要設定對資料工作台伺服器的存取權**

1. 導覽至您安裝資料工作台伺服器(InsightServer64.exe)之目錄中的「存取控制」檔案夾。

   範例: [!DNL C:\Adobe\Server\Access Control]

1. 在文 [!DNL Access Control.cfg] 字編輯器（如記事本）中開啟。
1. 找到此 [!DNL Report Server AccessGroup] 組並 [!DNL Report Server’s] 添加公用名稱，如以下檔案片段中突出顯示的。 (鍵入公用名稱，與數位憑證上顯示的 [!DNL Report Server’s] 名稱完全相同)。

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
