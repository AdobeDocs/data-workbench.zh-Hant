---
description: 管理員可以將管理自訂群組存取權控制的部份權限授予工作站使用者。
title: 對群組成員存取權進行使用者管理
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 6%

---

# 對群組成員存取權進行使用者管理{#user-administration-of-group-member-access}

{{eol}}

管理員可以將管理自訂群組存取權控制的部份權限授予工作站使用者。

**自我管理群組成員存取權** 為非管理員提供新增和刪除自訂群組成員的權限。 管理員會建立 **使用者清單** 檔案，並在 [Access Control.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) 檔案。

**訪問伺服器管理器**

設定 **[!DNL User List]** 檔案，並與同步 **[!DNL Communications.cfg]** 檔案在 **伺服器管理員** 工作區。

1. 在操作台上，按一下 **管理** 標籤> **資料集和設定檔** 標籤。

1. 開啟 **伺服器管理員** 工作區。
1. 按一下滑鼠右鍵>*您的伺服器名稱*> ，並選取 **檔案**.

   伺服器檔案將在帶列的表中開啟 *檔案*, *`<server name>`*，和 *臨時*.

1. **使本地** 按一下右鍵伺服器檔案的「伺服器」列（針對此功能） **[!DNL Access Control]** 和 **[!DNL Components/Communications.cfg)]**.

   白色勾選記號會顯示在 **臨時** 欄。 您可以在「臨時」資料夾中編輯。 然後以滑鼠右鍵按一下核取記號， **保存到** 伺服器。 （與伺服器同步時會變成紅色）。

## 建立User List.cfg檔案 {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

管理員需要建立 **[!DNL User List.cfg]** 檔案 **[!DNL Access Control]** 檔案夾。

1. 按一下右鍵** Access Control**行(位於 **臨時** 欄和選取 **開啟** > **資料夾**. ![](assets/6_4_workstation_groups_3.png)

   位於 **臨時** 資料夾會開啟，列出單一 **[!DNL Access Control.cfg]** 檔案。

1. 將其他文本檔案添加到此資料夾並將其命名 **[!DNL User List.cfg]** (在 **[!DNL Access Control.cfg]**)。

1. 將下列參數新增至 **[!DNL User List.cfg]** 檔案。

使用者清單檔案應包含的向量為 **AccessGroup** 對象和每個 **AccessGroup** 物件應具有名稱，且為字串的向量，稱為 **成員**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

然後，您可以在的「工作站」檢視中編輯和新增使用者**[!DNL User List.cfg]**檔案。

![](assets/6_4_workstation_groups_4.png)

以下是要新增至 **[!DNL User List.cfg]** 檔案。 然後，可在「工作站」視圖中添加成員。

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>與任何 **[!DNL .cfg]** 要手動編輯的檔案，請務必使用空格而非索引標籤，並密切注意空格和語法。 此檔案中的錯誤將導致 *Adobe Insight伺服器* 忽略用戶清單檔案。

此 **名稱** 欄位 **存取群組** 將在 [!DNL Access Control.cfg] 檔案。

>[!NOTE]
>
>只有具有目錄服務前置詞的有效成員，例如 **CN:** 或 **OU:** 接受，且不能包含萬用字元(&#42;)。

## 設定Communications.cfg檔案 {#section-9d6f05ba81c14f15be63e361533459e8}

管理員首先會開啟 **[!DNL Components]>[!DNL Communications.cfg]** 檔案和添加名稱為的新密鑰 **[!DNL Access Control User List File]**. 此索引鍵的字串值是新檔案所在的路徑。

1. 在伺服器檔案中，按一下 **元件** 並按一下右鍵「伺服器」列中的複選標籤。 按一下 **使本地**.

   白色勾選記號會顯示在 **臨時** 欄。

1. 以滑鼠右鍵按一下 **臨時** 欄和選取 **開啟** > **在工作站中**.

1. 在 **Communication.cfg** 檔案，按一下右鍵 **元件** 選取 **新增自訂金鑰。** ![](assets/6_4_workstation_groups.png)

1. 輸入 **名稱** as *訪問控制用戶清單檔案* 設定 **類型** as *字串*.

   >[!NOTE]
   >
   >不能將新清單檔案建立為路徑。 若要修正此問題，您需要儲存檔案，在編輯器（記事本）中開啟該檔案，並將「字串」變更為「路徑」：

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

1. 儲存 **[!DNL Communications.cfg]** 檔案，並（如有必要）將其儲存至伺服器。 這會重新啟動伺服器中的元件，以確保您未犯任何可能防止 **[!DNL Communications.cfg]** 檔案。
1. 如果您的系統包含處理伺服器，請修改 **[!DNL Components for Processing Servers.cfg]** 檔案。
1. 按一下右鍵 **[!DNL Communications.cfg]** 並保存到伺服器。

Data Workbench管理員現在可以確認目標使用者有權存取使用者清單檔案，並允許使用者管理群組。 用戶將能夠開啟用戶清單檔案，編輯該檔案，並根據需要添加和刪除CN或OU成員。

## 同步Access Control.cfg檔案 {#section-ca6da453dfb4432bb40b86ef15ede872}

然後，管理員就可以編輯 **[!DNL Access Control.cfg]** 和插入對由 *使用者清單* 檔案。

對組的引用應與任何其他成員一樣插入，但應使用以下語法：

```
$(Group Name)
```

其中「群組名稱」與使用者清單檔案中定義的項目相符，包括空格。 ![](assets/6_4_workstation_groups_2.png)

此時，Data Workbench管理員可確認選取的群組使用者是否擁有使用者清單檔案的存取權。 然後，選取的使用者可以開啟 **[!DNL User List.cfg]** 檔案，編輯它，並根據需要添加和刪除CN或OU成員。
