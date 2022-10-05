---
description: 新增帳戶的步驟。
title: 新增帳戶
uuid: 32081bc3-9050-42a2-95ad-85e7736fe5c4
exl-id: dabd1dd5-fcbf-4612-a240-89cafed2cf2e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 4%

---

# 新增帳戶{#adding-new-accounts}

{{eol}}

新增帳戶的步驟。

1. 在 [!DNL Report Portal]，按一下 **[!UICONTROL Admin]** 標籤。 此 [!DNL Admin] 頁。

   ![](assets/report_admintag2.png)

1. 在頁面右側，按一下 **[!UICONTROL new account]**. 此 [!DNL Create New Account] 頁。

   ![步驟資訊](assets/rptPort_scrn_AdminTab_createUser.png)

1. 按下表所示填寫此頁上的所有欄位：

   | 在此欄位中。.. | 指定分類的 . . . |
   |---|---|
   | 帳戶名稱 | 使用者登入時必須提供的帳戶名稱 [!DNL Report Portal]. |
   | 電子郵件 | 使用者或群組的電子郵件地址。 |
   | password | 用戶登錄時必須提供的密碼 [!DNL Report Portal]. |
   | 確認密碼 | 用戶登錄時必須提供的密碼 [!DNL Report Portal]. |
   | 設定檔存取 | 允許此使用者存取的設定檔（例如ProductSales）。 若要允許存取多個設定檔，請以逗號分隔名稱。 如果允許使用者存取與 [!DNL Report Portal]，鍵入&quot;ALL&quot;。 |
   | 標籤存取 | 允許此使用者存取的索引標籤(例如 [!DNL Admin])。 若要允許存取多個索引標籤，請以逗號分隔名稱。 如果允許使用者存取 [!DNL Report Portal]，鍵入&quot;ALL&quot;。 此欄位與帳戶類型欄位一起，對於定義群組存取權限非常有用。 |
   | 帳戶類型 | 此帳戶適用於個人或群組。 個別帳戶可讓使用者重設密碼，而群組則否。 管理員是唯一能夠重置組帳戶密碼的人。 |
   | 狀態 | 此帳戶是使用中還是非使用中。 預設值為活動值。 若要停用使用者帳戶，請選取非使用中。 |
   | admin | 是否允許此使用者建立、更新和刪除使用者帳戶，以及編輯與每個報表相關聯的附註。 預設設定為false。 若要將此變為管理員使用者，請選取true。 |
   | 到期日 | 此使用者可使用的日期(MM/DD/YYYY) [!DNL Report Portal]. |

1. 按一下 **[!UICONTROL insert]**。
