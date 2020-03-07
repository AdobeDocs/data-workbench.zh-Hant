---
description: 'null'
solution: Analytics
title: 新增使用者帳戶
topic: Data workbench
uuid: c322eeaa-a3f4-41e8-b38c-dd892ec29a87
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 新增使用者帳戶{#adding-a-user-account}

1. 按一下 **[!UICONTROL Add User]** 以開啟提示 **[!UICONTROL New User]** 符。

   ![](assets/add_user_account.png)

1. 填寫必要的欄位以完成表單。
   1. **[!UICONTROL Username]**:輸入用戶名。
   1. **[!UICONTROL Password]**:輸入長度超過6個字元的密碼。
   1. **[!UICONTROL Confirm Password]**:重新輸入密碼。
   1. **[!UICONTROL Authentication Method]**:從下拉式清單中選取選項。

      | **表單** | 依預設，控制面板會儲存使用者帳戶並在內部進行驗證。 |
      |---|---|
      | **LDAP** | 如果要通過LDAP驗證用戶，請選擇此選項。 （用戶必須已存在於目錄中）。 |
      | **Windows** | 選擇是否要使用Windows驗證來驗證用戶（用戶必須已存在於Windows目錄中）。 |

1. **[!UICONTROL Assigned Groups]**:從預設的「管理員」組和已建立的任何其他組中選擇。 目前不需要任何群組，而且使用者的群組成員資格隨時都可以修改。
1. 正確配置表單後，按一下 **[!UICONTROL Add User]** 將用戶添加到系統。

   如果操作成功，您會看到提示，指出已建立用戶。