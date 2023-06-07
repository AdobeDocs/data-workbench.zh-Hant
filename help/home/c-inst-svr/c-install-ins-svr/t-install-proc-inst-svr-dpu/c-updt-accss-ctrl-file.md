---
description: Access Control.cfg檔案可管理對Insight Server中特定功能的存取。
title: 更新存取控制檔案
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: 5ce5b8f8b35d2d4f319076f54347e300e5f133df
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 3%

---

# 更新存取控制檔案{#updating-the-access-control-file}

{{eol}}

Access Control.cfg檔案可管理對Insight Server中特定功能的存取。

它定義稱為AccessGroups的實體。 AccessGroup會識別具有使用伺服器特定功能之許可權的使用者群組。

連線到 [!DNL Insight Server] 替換為 [!DNL Insight]，您必須更新Administrators AccessGroup以包含其中一個 [!DNL Insight] Adobe已核發給貴組織的授權。 此AccessGroup會識別允許透過執行管理功能的使用者 [!DNL Insight].

下列程式說明如何將授權新增至Administrators AccessGroup。 若要完成此工作，您必須決定 [!DNL Insight] 授權擁有您組織的管理許可權。 (對於初始設定和設定，將管理許可權授予單一授權就足夠了。 您可以稍後將管理許可權授予其他授權。) 您還需要知道指派給此授權的「通用名稱」。

此程式的目的只是為了識別 [!DNL Insight] 可供您用來進行初始設定和設定的環境 [!DNL Insight Server]. 識別此授權後，您可以使用授權副本執行所有後續的伺服器設定（包括其他AccessGroup設定） [!DNL Insight]. 如需使用AccessGroups控制存取伺服器的其他資訊，請參閱 [設定存取控制](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**更新存取控制檔案**

1. 導覽至 [!DNL Access Control] 安裝目錄中的資料夾 [!DNL Insight Server].

   範例：[!DNL C:\Adobe\Server\Access Control]

1. 開啟 [!DNL Access Control.cfg] 文字編輯器（例如Notepad）中的檔案。
1. 在Administrators AccessGroup中找出CN專案，並以識別 [!DNL Insight] 用於初始設定和管理 [!DNL Insight Server]. 以下檔案片段說明您在中插入一般名稱的位置 [!DNL Access Control.cfg] 檔案。

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

   如果您使用憑證式驗證，則有一些額外的專案可用於設定。 這些專案包括：

   * O （組織ID）：此專案代表組織的ID。 例如，`1 = string: O:46F582D4582596B40A45491@ExampleOrg`。此ID可在Admin Console中找到。
   * PLC — 此專案允許存取為特定產品組態布建的使用者。 它可以用在格式中 `Organization_Id-PLC`. 例如，`1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。為使用PLC進行Data Workbench布建的使用者 `DataworkbenchAdminUsers` 將獲得其伺服器的存取權。
   * 電子郵件 — 此專案可存取任何個別使用者。 其值應為已布建使用者的電子郵件地址。 例如，`1 = string: Email:kim@exampleorg.com`。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 專案區分大小寫。 您必須確保為O、PLC和電子郵件指定的值與Admin Console中顯示的值完全相同。
   >    * 輸入與憑證上顯示的名稱完全相同的通用名稱。
   >    * 請勿使用Tab鍵在中產生空白字元 [!DNL Access Control.cfg] 檔案(或在Adobe元件的任何其他組態檔案中)。 僅使用空格來建立空白字元。 定位字元會導致系統無法正確讀取檔案。


1. 儲存並關閉檔案。
