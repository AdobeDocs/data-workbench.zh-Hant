---
description: Access Control.cfg檔案可管理對Insight Server中特定功能的存取。
solution: Insight
title: 更新訪問控制檔案
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 更新訪問控制檔案{#updating-the-access-control-file}

Access Control.cfg檔案可管理對Insight Server中特定功能的存取。

它定義名為AccessGroups的實體。 AccessGroup可識別一組具有使用伺服器某些功能權限的用戶。

您必須先更新「管 [!DNL Insight Server] 理員 [!DNL Insight]存取群組」，將Adobe已發給貴組織的其中一 [!DNL Insight] 份授權納入其中，才能連線至。 此AccessGroup可識別允許透過執行管理功能的使用者 [!DNL Insight]。

以下過程說明如何向Administrators AccessGroup添加許可證。 要完成此任務，您必須確定哪個許 [!DNL Insight] 可證具有組織的管理權限。 (對於初始設定和設定，授予單一授權的管理權限就足夠了。 您稍後可以將管理權限授予其他授權。)您也需要知道指派給此授權的「公用名稱」。 若要取得此值，請至https://aap.adobe.com檢查您帳戶的授權 [憑證](https://aap.adobe.com)。

此程式的目的只是為了識別您最初可 [!DNL Insight] 用來設定和設定的授權副本 [!DNL Insight Server]。 在您識別此授權後，即可使用授權副本執行所有後續的伺服器設定（包括其他AccessGroup設定） [!DNL Insight]。 有關使用AccessGroups控制對伺服器的訪問的其他資訊，請參 [閱配置訪問控制](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)。

**要更新訪問控制檔案**

1. 導覽至您 [!DNL Access Control] 所安裝目錄中的資料夾 [!DNL Insight Server]。

   範例: [!DNL C:\Adobe\Server\Access Control]

1. 在文本編 [!DNL Access Control.cfg] 輯器（如記事本）中開啟檔案。
1. 在Administrators AccessGroup中找到CN條目，並將此條目的現有值替換為公共名稱，該公共名稱標識您將用於初始設定 [!DNL Insight] 和管理的條目 [!DNL Insight Server]。 以下檔案片段說明了在檔案中插入公共名稱的 [!DNL Access Control.cfg] 位置。

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

   * O（組織ID）:此條目表示組織的ID。 例如, `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. 此ID可在「管理控制台」中找到。
   * PLC —— 此條目允許訪問為特定產品配置設定的用戶。 它可用於格式 `Organization_Id-PLC`。 例如, `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. 使用PLC為「資料工作台」布建的使 `DataworkbenchAdminUsers` 用者將可存取其伺服器。
   * 電子郵件——此項目可讓任何個別使用者存取。 其值應為已布建使用者的電子郵件地址。 例如, `1 = string: Email:kim@exampleorg.com`.
   >[!NOTE]
   >
   >
   >    
   >    
   >    * 條目區分大小寫。 您必須確保為O、PLC和電子郵件指定的值與管理控制台中顯示的值完全相同。
   >    * 鍵入公用名稱，與在憑證上顯示的名稱完全相同。
   >    * 請勿使用Tab鍵在檔案(或在Adobe元件的任 [!DNL Access Control.cfg] 何其他設定檔中)中產生空格。 僅使用空格來建立空格。 制表符會使系統無法正確讀取檔案。


1. 儲存並關閉檔案。

