---
description: Access Control.cfg檔案可管理對Insight Server中特定功能的存取。
title: 更新存取控制檔案
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# 更新存取控制檔案{#updating-the-access-control-file}

Access Control.cfg檔案可管理對Insight Server中特定功能的存取。

它定義名為AccessGroups的實體。 AccessGroup可識別一組具有使用伺服器某些功能權限的用戶。

您必須先更新「管理員存取群組」，以包含Adobe已發給您組織的[!DNL Insight]授權，才能連線至[!DNL Insight Server]和[!DNL Insight]。 此AccessGroup標識允許通過[!DNL Insight]執行管理功能的用戶。

以下過程說明如何向Administrators AccessGroup添加許可證。 要完成此任務，您必須確定哪個[!DNL Insight]許可證對您的組織具有管理權限。 (對於初始設定和設定，授予單一授權的管理權限就足夠了。 您稍後可以將管理權限授予其他授權。) 您也需要知道指派給此授權的「公用名稱」。 若要取得此值，請至[https://aap.adobe.com](https://aap.adobe.com)檢查您帳戶的授權憑證。

此程式的目的只是為了識別[!DNL Insight]的授權副本，您可用於初始設定和配置[!DNL Insight Server]。 在您識別此授權後，您就可以使用[!DNL Insight]的授權副本執行所有後續的伺服器設定（包括其他AccessGroup設定）。 有關使用AccessGroups控制對伺服器的訪問的其他資訊，請參見[配置訪問控制](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)。

**要更新訪問控制檔案**

1. 導覽至安裝[!DNL Insight Server]之目錄的[!DNL Access Control]資料夾。

   範例：[!DNL C:\Adobe\Server\Access Control]

1. 在文本編輯器（如記事本）中開啟[!DNL Access Control.cfg]檔案。
1. 在Administrators AccessGroup中找到CN條目，並將此條目的現有值替換為用於標識[!DNL Insight]的公用名稱，該公用名稱用於初始設定和管理[!DNL Insight Server]。 以下檔案片段說明了在[!DNL Access Control.cfg]檔案中插入公用名稱的位置。

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

   如果您使用基於憑據的驗證，將有一些額外條目可用於配置。 這些條目包括：

   * O（組織ID）:此條目表示組織的ID。 例如：`1 = string: O:46F582D4582596B40A45491@ExampleOrg`。此ID可在Admin Console中找到。
   * PLC —— 此條目允許訪問為特定產品配置設定的用戶。 它可用於格式`Organization_Id-PLC`。 例如：`1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。使用PLC `DataworkbenchAdminUsers`布建的Data Workbench用戶將訪問其伺服器。
   * 電子郵件——此項目可讓任何個別使用者存取。 其值應為已布建使用者的電子郵件地址。 例如：`1 = string: Email:kim@exampleorg.com`。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 條目區分大小寫。 您必須確保為O、PLC和電子郵件指定的值與Admin Console中顯示的值完全相同。
   >    * 鍵入公用名稱，與在憑證上顯示的名稱完全相同。
   >    * 請勿使用Tab鍵在[!DNL Access Control.cfg]檔案(或在Adobe元件的任何其他配置檔案中)中生成空格。 僅使用空格來建立空格。 制表符會使系統無法正確讀取檔案。


1. 儲存並關閉檔案。
