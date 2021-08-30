---
description: 管理員可以將管理自訂群組存取權控制的部份權限授予工作站使用者。
title: 對群組成員存取權進行使用者管理
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 6%

---

# 對群組成員存取權進行使用者管理{#user-administration-of-group-member-access}

管理員可以將管理自訂群組存取權控制的部份權限授予工作站使用者。

**自行管理群組成員存取** 權可讓非管理員新增和刪除自訂群組中的成員。管理員建立&#x200B;**用戶清單**&#x200B;檔案，並在[Access Control.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html)檔案中為新組成員設定組訪問。

**訪問伺服器管理器**

在&#x200B;**伺服器管理器**&#x200B;工作區中設定&#x200B;**[!DNL User List]**&#x200B;檔案並與&#x200B;**[!DNL Communications.cfg]**&#x200B;檔案同步。

1. 在操作台上，按一下「**管理** 」標籤> **資料集和設定檔** 」標籤。

1. 開啟&#x200B;**伺服器管理器**&#x200B;工作區。
1. 按一下右鍵圖中的>*您的伺服器名稱*，然後選擇&#x200B;**檔案**。

   伺服器檔案將在表中開啟，其中列&#x200B;*File*、*`<server name>`*&#x200B;和&#x200B;*Temp*。

1. **在伺** 服器檔案的伺服器欄中按一下滑鼠右鍵，使其成為本地(針對此功能 **[!DNL Access Control]** 和 **[!DNL Components/Communications.cfg)]**)。

   在&#x200B;**Temp**&#x200B;欄中會出現白色勾號。 您可以在「臨時」資料夾中編輯。 然後，按一下右鍵複選標籤，然後&#x200B;**Save To**&#x200B;伺服器。 （與伺服器同步時會變成紅色）。

## 建立User List.cfg檔案 {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

管理員需要在&#x200B;**[!DNL Access Control]**&#x200B;資料夾中建立&#x200B;**[!DNL User List.cfg]**&#x200B;檔案。

1. 按一下右鍵&#x200B;**Temp**&#x200B;列中的** Access Control**行，然後選擇&#x200B;**Open** > **Folder**。 ![](assets/6_4_workstation_groups_3.png)

   **Temp**&#x200B;資料夾中的Access Control資料夾將開啟一個&#x200B;**[!DNL Access Control.cfg]**&#x200B;檔案。

1. 將另一個文本檔案添加到此資料夾，並將其命名為&#x200B;**[!DNL User List.cfg]**（**[!DNL Access Control.cfg]**&#x200B;旁）。

1. 將下列參數新增至&#x200B;**[!DNL User List.cfg]**&#x200B;檔案。

用戶清單檔案應包含&#x200B;**AccessGroup**&#x200B;對象的向量，每個&#x200B;**AccessGroup**&#x200B;對象應具有名稱和字串的向量，該字串名為&#x200B;**Members**。

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

然後，您可以在**[!DNL User List.cfg]**檔案的「工作站」檢視中編輯和新增使用者。

![](assets/6_4_workstation_groups_4.png)

以下是要新增至&#x200B;**[!DNL User List.cfg]**&#x200B;檔案的最基本參數。 然後，可在「工作站」視圖中添加成員。

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>和您手動編輯的任何&#x200B;**[!DNL .cfg]**&#x200B;檔案一樣，請務必使用空格而非索引標籤，並密切注意空格和語法。 此檔案中的錯誤將導致&#x200B;*Adobe Insight伺服器*&#x200B;忽略用戶清單檔案。

每個&#x200B;**存取群組**&#x200B;中的&#x200B;**名稱**&#x200B;欄位將在[!DNL Access Control.cfg]檔案中參考。

>[!NOTE]
>
>僅接受具有目錄服務前置詞的有效成員，如&#x200B;**CN:**&#x200B;或&#x200B;**OU:**，這些成員不能包含通配符(*)。

## 設定Communications.cfg檔案 {#section-9d6f05ba81c14f15be63e361533459e8}

管理員首先啟用此功能，方法是開啟&#x200B;**[!DNL Components]>[!DNL Communications.cfg]**&#x200B;檔案並添加名為&#x200B;**[!DNL Access Control User List File]**&#x200B;的新密鑰。 此索引鍵的字串值是新檔案所在的路徑。

1. 在伺服器檔案中，按一下&#x200B;**元件**&#x200B;並按一下右鍵伺服器列中的複選標籤。 按一下「**Make Local**」。

   在&#x200B;**Temp**&#x200B;欄中會出現白色勾號。

1. 按一下右鍵&#x200B;**Temp**&#x200B;列中的複選標籤，然後在Workstation **中選擇** Open **>**。

1. 在&#x200B;**Communication.cfg**&#x200B;檔案中，按一下右鍵&#x200B;**component**&#x200B;並選擇&#x200B;**Add Custom Key.** ![](assets/6_4_workstation_groups.png)

1. 鍵入&#x200B;**Name**&#x200B;作為&#x200B;*Access Control用戶清單檔案*，並將&#x200B;**類型**&#x200B;設定為&#x200B;*String*。

   >[!NOTE]
   不能將新清單檔案建立為路徑。 若要修正此問題，您需要儲存檔案，在編輯器（記事本）中開啟該檔案，並將「字串」變更為「路徑」：

   在可以記錄:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <string>: Access Control\\User List.cfg
   ```

   之後:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <Path>: Access Control\\User List.cfg
   ```

1. 保存&#x200B;**[!DNL Communications.cfg]**&#x200B;檔案，並（如果必要）將其保存到伺服器。 這將重新啟動伺服器中的元件，以確保您未犯任何可能阻止剖析&#x200B;**[!DNL Communications.cfg]**&#x200B;檔案的錯誤。
1. 如果您的系統包含處理伺服器，請修改&#x200B;**[!DNL Components for Processing Servers.cfg]**&#x200B;檔案中的配置檔案。
1. 按一下右鍵&#x200B;**[!DNL Communications.cfg]**&#x200B;並保存到伺服器。

Data Workbench管理員現在可以確認目標使用者有權存取使用者清單檔案，並允許使用者管理群組。 用戶將能夠開啟用戶清單檔案、編輯該檔案，並根據需要添加和刪除CN或OU成員。

## 同步Access Control.cfg檔案 {#section-ca6da453dfb4432bb40b86ef15ede872}

然後，管理員可以編輯&#x200B;**[!DNL Access Control.cfg]**&#x200B;並插入對&#x200B;*用戶清單*&#x200B;檔案定義的組的引用。

對組的引用應與任何其他成員一樣插入，但應使用以下語法：

```
$(Group Name)
```

其中「群組名稱」與使用者清單檔案中定義的項目相符，包括空格。![](assets/6_4_workstation_groups_2.png)

此時，Data Workbench管理員可確認選取的群組使用者是否擁有使用者清單檔案的存取權。 然後，選擇用戶可以開啟&#x200B;**[!DNL User List.cfg]**&#x200B;檔案，編輯該檔案，並根據需要添加和刪除CN或OU成員。
