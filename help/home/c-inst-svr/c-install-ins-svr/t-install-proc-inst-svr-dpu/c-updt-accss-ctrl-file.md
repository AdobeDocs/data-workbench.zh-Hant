---
description: Access Control.cfg檔案可管理對Insight Server中特定功能的存取。
title: 更新存取控制檔案
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# 更新存取控制檔案{#updating-the-access-control-file}

Access Control.cfg檔案可管理對Insight Server中特定功能的存取。

它定義名為AccessGroups的實體。 AccessGroup標識了一組有權使用伺服器的某些功能的用戶。

在使用[!DNL Insight]連接到[!DNL Insight Server]之前，必須更新Administrators AccessGroup以包括Adobe已發給您的組織的[!DNL Insight]許可證之一。 此AccessGroup標識允許通過[!DNL Insight]執行管理功能的用戶。

以下過程說明如何向Administrators AccessGroup添加許可證。 要完成此任務，必須確定哪個[!DNL Insight]許可證對貴組織具有管理權限。 (對於初始設定和配置，授予單個許可證的管理權限就足夠了。 您稍後可以授予其他授權的管理權限。) 您還需要知道指派給此授權的「通用名稱」。 若要取得此值，您可以前往[https://aap.adobe.com](https://aap.adobe.com)檢查您帳戶的授權憑證。

此過程的目的只是標識一個許可的[!DNL Insight]副本，您可以用於初始設定和配置[!DNL Insight Server]。 在您標識此許可證後，可以使用許可副本[!DNL Insight]執行所有後續伺服器配置（包括其他AccessGroup配置）。 有關使用AccessGroups控制對伺服器的訪問的其他資訊，請參見[配置訪問控制](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)。

**更新訪問控制檔案**

1. 導覽至[!DNL Insight Server]安裝目錄中的[!DNL Access Control]資料夾。

   範例：[!DNL C:\Adobe\Server\Access Control]

1. 在文本編輯器（如記事本）中開啟[!DNL Access Control.cfg]檔案。
1. 在Administrators AccessGroup中找到CN條目，並將該條目的現有值替換為用於初始設定和管理[!DNL Insight Server]的公共名稱。 [!DNL Insight]以下檔案片段說明在[!DNL Access Control.cfg]檔案中插入公用名稱的位置。

   ```
   Access Control Groups = vector: 5 items 
     0 = AccessGroup: 
       Members = vector: 2 items 
         0 = string: IP:127.0.0.1 
         1 = string: CN: CommonName 
       Name = string: Administrators 
       Read-Only Access = vector: 0 items 
       Read-Write Access = vector: 1 items 
         0 = string: / 
     1 = AccessGroup: 
     . . . 
   ```

   如果您使用的是憑證式驗證，則可以設定一些額外項目。 這些項目包括：

   * O（組織ID）:此項目代表組織的ID。 例如：`1 = string: O:46F582D4582596B40A45491@ExampleOrg`。可在Admin Console中找到此ID。
   * PLC — 此條目允許訪問為特定產品配置而配置的用戶。 它可用於`Organization_Id-PLC`格式。 例如：`1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。使用PLC `DataworkbenchAdminUsers`為Data Workbench布建的用戶將在其伺服器上獲得訪問權限。
   * 電子郵件 — 此條目允許訪問任何個別用戶。 其值應為已布建使用者的電子郵件地址。 例如：`1 = string: Email:kim@exampleorg.com`。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 項區分大小寫。 您必須確保為O、PLC和Email指定的值與Admin Console中顯示的值完全相同。
   >    * 輸入與憑證上完全相同的通用名稱。
   >    * 請勿使用Tab鍵在[!DNL Access Control.cfg]檔案(或Adobe元件的任何其他配置檔案)中產生空白字元。 僅使用空格來建立空格。 制表符字元使系統無法正確讀取檔案。


1. 儲存並關閉檔案。
