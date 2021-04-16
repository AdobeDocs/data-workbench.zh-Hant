---
description: 編輯現有使用者帳戶的步驟。
title: 編輯現有使用者
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
exl-id: cfbc54d8-16b4-4629-b556-a2aa4ee0c606
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 3%

---

# 編輯現有使用者{#editing-existing-users}

編輯現有使用者帳戶的步驟。

1. 在[!DNL Report Portal]中，按一下&#x200B;**[!UICONTROL Admin]**&#x200B;頁籤。 此時將顯示[!DNL Admin]頁。

   ![](assets/report_admintag2.png)

1. 按一下代表您要編輯之帳戶名稱第一個字母的字母。 例如，如果您想要編輯帳戶「行銷」，請按一下字母「M」。

   隨即顯示以該字母開頭的帳戶名稱清單。

1. 選擇您要編輯的帳戶名稱，然後按一下&#x200B;**[!UICONTROL select]**&#x200B;按鈕。 此時將顯示[!DNL Edit Account Info]頁。

   ![步驟資訊](assets/rptPort_scrn_AdminTab_editUser.png)

1. 僅變更此頁面上需要更新的欄位。 下表說明這些欄位：

   | 在此欄位中。.. | 指定分類的 . . . |
   |---|---|
   | 電子郵件 | 使用者的電子郵件地址。 |
   | 舊密碼 | 目前的密碼，在編輯管理員帳戶或重設非管理員帳戶的密碼時需要繼續。 |
   | 新密碼 | 用戶登錄[!DNL Report Portal]時必須提供的新密碼。 |
   | 確認密碼 | 用戶登錄[!DNL Report Portal]時必須提供的新密碼。 |
   | 設定檔存取 | 此使用者可存取的設定檔（例如ProductSales）。 若要允許存取多個描述檔，請以逗號分隔名稱。 如果允許用戶訪問與[!DNL Report Portal]關聯的所有配置檔案，請鍵入「ALL」。 |
   | 頁籤訪問 | 允許此用戶訪問的頁籤（例如[!DNL Admin]）。 若要允許存取多個標籤，請以逗號分隔名稱。 如果允許用戶訪問[!DNL Report Portal]中的所有頁籤，請鍵入「ALL」。 此欄位與帳戶類型欄位搭配使用，對於定義群組存取權非常有用。 |
   | 帳戶類型 | 此帳戶是針對個人或群組。 個別帳戶可讓使用者重設密碼，而群組則不會。 管理員是唯一能夠重設群組帳戶密碼的人員。 |
   | 狀態 | 此帳戶是活動中還是非活動中。 預設值為活動值。 若要停用使用者帳戶，請選取&#x200B;**[!UICONTROL inactive]**。 |
   | admin | 是否允許此使用者建立、更新和刪除使用者帳戶，以及編輯與每個報表關聯的附註。 預設設定為false。 若要將此設為管理員使用者，請選取true。 |
   | 到期日 | 此日期的格式為MM/DD/YYYY，直到允許此用戶使用[!DNL Report Portal]。 |

1. 按一下 **[!UICONTROL update]**。
