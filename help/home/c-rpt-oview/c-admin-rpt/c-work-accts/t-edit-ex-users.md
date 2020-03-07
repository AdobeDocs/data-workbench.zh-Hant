---
description: 編輯現有使用者帳戶的步驟。
solution: Analytics
title: 編輯現有使用者
topic: Data workbench
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 編輯現有使用者{#editing-existing-users}

編輯現有使用者帳戶的步驟。

1. 在中， [!DNL Report Portal]按一下該選 **[!UICONTROL Admin]** 項卡。 此時將 [!DNL Admin] 顯示頁面。

   ![](assets/report_admintag2.png)

1. 按一下代表您要編輯之帳戶名稱第一個字母的字母。 例如，如果您想要編輯帳戶「行銷」，請按一下字母「M」。

   此時會顯示以該字母開始的帳戶名稱清單。

1. 選取您要編輯的帳戶名稱，然後按一下按 **[!UICONTROL select]** 鈕。 此時將 [!DNL Edit Account Info] 顯示頁面。

   ![步驟資訊](assets/rptPort_scrn_AdminTab_editUser.png)

1. 僅變更此頁面上需要更新的欄位。 下表說明這些欄位：

   | 在此欄位中。.. | 指定分類的 . . . |
   |---|---|
   | 電子郵件 | 使用者的電子郵件地址。 |
   | 舊密碼 | 目前的密碼，在編輯管理員帳戶或重設非管理員帳戶的密碼時需要繼續。 |
   | 新密碼 | 用戶登錄時必須提供的新密碼 [!DNL Report Portal]。 |
   | 確認密碼 | 用戶登錄時必須提供的新密碼 [!DNL Report Portal]。 |
   | 設定檔存取 | 此使用者可存取的設定檔（例如ProductSales）。 若要允許存取多個描述檔，請以逗號分隔名稱。 如果允許用戶訪問與關聯的所有配置檔案， [!DNL Report Portal]請鍵入「ALL」。 |
   | 頁籤訪問 | 此使用者可存取的標籤(例如 [!DNL Admin])。 若要允許存取多個標籤，請以逗號分隔名稱。 如果允許用戶訪問中的所有頁籤， [!DNL Report Portal]請鍵入「ALL」。此欄位與帳戶類型欄位搭配使用，對於定義群組存取權非常有用。 |
   | 帳戶類型 | 此帳戶是針對個人或群組。 個別帳戶可讓使用者重設密碼，而群組則不會。 管理員是唯一能夠重設群組帳戶密碼的人員。 |
   | 狀態 | 此帳戶是活動中還是非活動中。 預設值為活動值。 若要停用使用者帳戶，請選取 **[!UICONTROL inactive]**。 |
   | admin | 是否允許此使用者建立、更新和刪除使用者帳戶，以及編輯與每個報表關聯的附註。 預設設定為false。 若要將此設為管理員使用者，請選取true。 |
   | 到期日 | 該日期的格式為MM/DD/YYYY，直到允許該用戶使用為止 [!DNL Report Portal]。 |

1. 按一下 **[!UICONTROL update]**.
