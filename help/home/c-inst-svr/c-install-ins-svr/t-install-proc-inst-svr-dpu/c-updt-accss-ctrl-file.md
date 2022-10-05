---
description: Access Control.cfg檔案可管理對Insight Server中特定功能的存取。
title: 更新存取控制檔案
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# 更新存取控制檔案{#updating-the-access-control-file}

{{eol}}

Access Control.cfg檔案可管理對Insight Server中特定功能的存取。

它定義名為AccessGroups的實體。 AccessGroup標識了一組有權使用伺服器的某些功能的用戶。

在您可以連線至之前 [!DNL Insight Server] with [!DNL Insight]，您必須更新「管理員存取群組」以包含 [!DNL Insight] Adobe已核發給貴組織的授權。 此AccessGroup標識允許通過以下方式執行管理功能的用戶： [!DNL Insight].

以下過程說明如何向Administrators AccessGroup添加許可證。 要完成此任務，必須確定 [!DNL Insight] 授權對貴組織具有管理權限。 (對於初始設定和配置，授予單個許可證的管理權限就足夠了。 您稍後可以授予其他授權的管理權限。) 您還需要知道指派給此授權的「通用名稱」。 若要取得此值，您可以在 [https://aap.adobe.com](https://aap.adobe.com).

此程式的目的只是為了確定 [!DNL Insight] 供您最初設定及設定 [!DNL Insight Server]. 在您標識此許可證後，您可以使用的許可副本執行所有後續伺服器配置（包括其他AccessGroup配置） [!DNL Insight]. 有關使用AccessGroups控制對伺服器的訪問的其他資訊，請參見 [配置訪問控制](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**更新訪問控制檔案**

1. 導覽至 [!DNL Access Control] 資料夾（位於安裝的目錄中） [!DNL Insight Server].

   範例：[!DNL C:\Adobe\Server\Access Control]

1. 開啟 [!DNL Access Control.cfg] 檔案（如記事本）。
1. 在Administrators AccessGroup中找到CN條目，並將此條目的現有值替換為標識 [!DNL Insight] 您最初將用來設定和管理 [!DNL Insight Server]. 下列檔案片段說明如何在 [!DNL Access Control.cfg] 檔案。

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

   * O（組織ID）:此項目代表組織的ID。 例如，`1 = string: O:46F582D4582596B40A45491@ExampleOrg`。可在Admin Console中找到此ID。
   * PLC — 此條目允許訪問為特定產品配置而配置的用戶。 可用於格式 `Organization_Id-PLC`. 例如，`1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。使用PLC為Data Workbench預配的用戶 `DataworkbenchAdminUsers` 將在其伺服器上訪問。
   * 電子郵件 — 此條目允許訪問任何個別用戶。 其值應為已布建使用者的電子郵件地址。 例如，`1 = string: Email:kim@exampleorg.com`。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 項區分大小寫。 您必須確保為O、PLC和Email指定的值與Admin Console中顯示的值完全相同。
   >    * 輸入與憑證上完全相同的通用名稱。
   >    * 請勿使用Tab鍵來產生空白字元 [!DNL Access Control.cfg] 檔案(或Adobe元件的任何其他設定檔案)。 僅使用空格來建立空格。 制表符字元使系統無法正確讀取檔案。


1. 儲存並關閉檔案。
