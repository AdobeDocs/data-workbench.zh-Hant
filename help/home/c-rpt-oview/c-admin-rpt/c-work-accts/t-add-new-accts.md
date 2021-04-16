---
description: 新增帳戶的步驟。
title: 新增帳戶
uuid: 32081bc3-9050-42a2-95ad-85e7736fe5c4
exl-id: dabd1dd5-fcbf-4612-a240-89cafed2cf2e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 4%

---

# 新增帳戶{#adding-new-accounts}

新增帳戶的步驟。

1. 在[!DNL Report Portal]中，按一下&#x200B;**[!UICONTROL Admin]**&#x200B;頁籤。 此時將顯示[!DNL Admin]頁。

   ![](assets/report_admintag2.png)

1. 在頁面的右側，按一下&#x200B;**[!UICONTROL new account]**。 此時將顯示[!DNL Create New Account]頁。

   ![步驟資訊](assets/rptPort_scrn_AdminTab_createUser.png)

1. 按下表所示填寫此頁上的所有欄位：

   | 在此欄位中。.. | 指定分類的 . . . |
   |---|---|
   | 帳戶名稱 | 登入[!DNL Report Portal]時，使用者必須提供的帳戶名稱。 |
   | 電子郵件 | 使用者或群組的電子郵件地址。 |
   | password | 登錄[!DNL Report Portal]時用戶必須提供的口令。 |
   | 確認密碼 | 登錄[!DNL Report Portal]時用戶必須提供的口令。 |
   | 設定檔存取 | 此使用者可存取的設定檔（例如ProductSales）。 若要允許存取多個描述檔，請以逗號分隔名稱。 如果允許用戶訪問與[!DNL Report Portal]關聯的所有配置檔案，請鍵入「ALL」。 |
   | 頁籤訪問 | 允許此用戶訪問的頁籤（例如[!DNL Admin]）。 若要允許存取多個標籤，請以逗號分隔名稱。 如果允許用戶訪問[!DNL Report Portal]中的所有頁籤，請鍵入「ALL」。 此欄位與帳戶類型欄位搭配使用，對於定義群組存取權非常有用。 |
   | 帳戶類型 | 此帳戶是針對個人或群組。 個別帳戶可讓使用者重設密碼，而群組則不會。 管理員是唯一能夠重設群組帳戶密碼的人員。 |
   | 狀態 | 此帳戶是活動中還是非活動中。 預設值為活動值。 若要停用使用者帳戶，請選取非活動中。 |
   | admin | 是否允許此使用者建立、更新和刪除使用者帳戶，以及編輯與每個報表關聯的附註。 預設設定為false。 若要將此設為管理員使用者，請選取true。 |
   | 到期日 | 此日期的格式為MM/DD/YYYY，直到允許此用戶使用[!DNL Report Portal]。 |

1. 按一下 **[!UICONTROL insert]**。
