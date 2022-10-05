---
description: 新增使用者帳戶
title: 新增使用者帳戶
uuid: c322eeaa-a3f4-41e8-b38c-dd892ec29a87
exl-id: c99f3189-4d89-443a-be5b-84352c4ec6e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 8%

---

# 新增使用者帳戶{#adding-a-user-account}

{{eol}}

1. 按一下 **[!UICONTROL Add User]** 提起 **[!UICONTROL New User]** 提示。

   ![](assets/add_user_account.png)

1. 填寫必填欄位以完成表單。
   1. **[!UICONTROL Username]**:輸入用戶名。
   1. **[!UICONTROL Password]**:輸入長度超過6個字元的密碼。
   1. **[!UICONTROL Confirm Password]**:重新輸入密碼。
   1. **[!UICONTROL Authentication Method]**:從下拉式清單中選取選項。

      | **表單** | 依預設，控制面板會儲存使用者帳戶並進行內部驗證。 |
      |---|---|
      | **LDAP** | 如果要通過LDAP驗證用戶，請選擇此選項。 （目錄中必須已存在該用戶）。 |
      | **Windows** | 選擇是否要使用Windows身份驗證來驗證用戶（用戶必須已存在於Windows目錄中）。 |

1. **[!UICONTROL Assigned Groups]**:從預設的管理員組和已建立的任何其他組中選擇。 此時不需要任何組，並且可以隨時修改用戶的組成員資格。
1. 正確設定表單後，按一下 **[!UICONTROL Add User]** 將用戶添加到系統。

   如果操作成功，您會看到提示，指出已建立使用者。
