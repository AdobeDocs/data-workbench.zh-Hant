---
description: 編輯現有使用者帳戶的步驟。
title: 編輯現有使用者
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
exl-id: cfbc54d8-16b4-4629-b556-a2aa4ee0c606
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 3%

---

# 編輯現有使用者{#editing-existing-users}

{{eol}}

編輯現有使用者帳戶的步驟。

1. 在 [!DNL Report Portal]，按一下 **[!UICONTROL Admin]** 標籤。 此 [!DNL Admin] 頁。

   ![](assets/report_admintag2.png)

1. 按一下代表您要編輯之帳戶名稱第一個字母的字母。 例如，如果您想要編輯帳戶「行銷」，請按一下字母「M」。

   隨即顯示以該信函開頭的帳戶名稱清單。

1. 選取您要編輯的帳戶名稱，然後按一下 **[!UICONTROL select]** 按鈕。 此 [!DNL Edit Account Info] 頁。

   ![步驟資訊](assets/rptPort_scrn_AdminTab_editUser.png)

1. 僅變更此頁面上需要更新的欄位。 下表提供以下各欄位的說明：

   | 在此欄位中。.. | 指定分類的 . . . |
   |---|---|
   | 電子郵件 | 使用者的電子郵件地址。 |
   | 舊密碼 | 編輯管理員帳戶或重設非管理員帳戶的密碼時需要繼續使用的目前密碼。 |
   | 新密碼 | 用戶登錄時必須提供的新密碼 [!DNL Report Portal]. |
   | 確認密碼 | 用戶登錄時必須提供的新密碼 [!DNL Report Portal]. |
   | 設定檔存取 | 允許此使用者存取的設定檔（例如ProductSales）。 若要允許存取多個設定檔，請以逗號分隔名稱。 如果允許使用者存取與 [!DNL Report Portal]，鍵入&quot;ALL&quot;。 |
   | 標籤存取 | 允許此使用者存取的索引標籤(例如 [!DNL Admin])。 若要允許存取多個索引標籤，請以逗號分隔名稱。 如果允許使用者存取 [!DNL Report Portal]，鍵入&quot;ALL&quot;。 此欄位與帳戶類型欄位一起，對於定義群組存取權限非常有用。 |
   | 帳戶類型 | 此帳戶適用於個人或群組。 個別帳戶可讓使用者重設密碼，而群組則否。 管理員是唯一能夠重置組帳戶密碼的人。 |
   | 狀態 | 此帳戶是使用中還是非使用中。 預設值為活動值。 若要停用使用者帳戶，請選取 **[!UICONTROL inactive]**. |
   | admin | 是否允許此使用者建立、更新和刪除使用者帳戶，以及編輯與每個報表相關聯的附註。 預設設定為false。 若要將此變為管理員使用者，請選取true。 |
   | 到期日 | 此使用者可使用的日期(MM/DD/YYYY) [!DNL Report Portal]. |

1. 按一下 **[!UICONTROL update]**。
