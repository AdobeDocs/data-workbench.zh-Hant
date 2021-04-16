---
description: 下載並安裝數位憑證的步驟。
title: 數位憑證安裝程序
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
exl-id: a8ae8d23-8db8-44d9-8c45-e552da81c384
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 33%

---

# 數位憑證安裝程序{#digital-certificate-installation-procedures}

下載並安裝數位憑證的步驟。

1. 開啟網路瀏覽器，前往 [https://aap.adobe.com](https://aap.adobe.com)。

   >[!NOTE]
   >
   >您的瀏覽器可能會在這時提示您提供數位憑證。如果是，只需按一下&#x200B;**[!UICONTROL Cancel]**&#x200B;即可關閉對話方塊。

1. 在登入畫面中，輸入您從Adobe收到的帳戶名稱和密碼，然後按一下&#x200B;**[!UICONTROL login]**。
1. 找到為[!DNL Report]伺服器實例（*您的名稱*.pem）頒發的證書，然後按一下與該證書關聯的![](assets/btn_save_certificatedownload.PNG)表徵圖。
1. 提示儲存憑證時，請按一下「**[!UICONTROL Save]**」。
1. 將檔案下載到[!DNL Report Server]安裝目錄的「證書」資料夾。

   此檔案夾已有憑證檔案「[!DNL trust_ca_cert.pem]」。[!DNL Report]伺服器必須始終存在兩個證書檔案才能正常工作。
