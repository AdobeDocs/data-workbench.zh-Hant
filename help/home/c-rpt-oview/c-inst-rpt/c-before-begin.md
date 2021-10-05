---
description: 為了讓報表伺服器的某些功能發揮作用，您必須先提供並配置硬體或軟體，然後才能安裝。
title: 開始之前
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---

# 開始之前{#before-you-begin}

為了讓報表伺服器的某些功能發揮作用，您必須先提供並配置硬體或軟體，然後才能安裝。

## 基本報表伺服器需求 {#section-e891eaee79fe4fa98e658426dc3b2777}

輸出的報表可以是.PNG影像或檔案系統中放置的.XLS電子錶格的形式，也可以是電子郵件形式。 硬體要求與[data workbench用戶端](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements)相同。

報表伺服器有下列需求：

* 訪問檔案系統以輸出資料（網路共用或本地驅動器）。
* 訪問配置的SMTP伺服器。
* Microsoft Excel 2010 64位元或更高版本，安裝在[!DNL Report]伺服器上。 如需詳細資訊，請參閱[伺服器端Office自動化考量事項](https://support.microsoft.com/kb/257757) 。

## 其他需求 {#section-f53d4388656a4dfc90aefe29dfabef89}

* **安裝適當的圖形適配器。** 要正確呈現報告，安裝伺服器的電 [!DNL Report] 腦必須安裝相應的圖形適配器。

* **安裝Microsoft Excel以以Excel檔案產生報表。** 若要以Microsoft Excel檔案( [!DNL .xls] 或 [!DNL .xlsx])產生和分發報表，您安裝Report Server的電腦必須安裝並註冊適當版本的64位元Microsoft Excel。如果Excel尚未註冊，且報表伺服器嘗試首次存取，則Excel會顯示註冊對話方塊。 如果您不確定副本是否已註冊，請手動啟動Excel，如果出現註冊對話框，請完成註冊過程。

   >[!NOTE]
   >
   >以Excel檔案產生報表時，會開啟新的Excel例項。 有關此過程的詳細資訊，請參閱[https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757)。

* **提供對SMTP伺服器的訪問，以通過電子郵件分發報告。** 如果要在電子郵件中分發報表，報表伺服器必須能夠連接到SMTP伺服器，並且必須開啟指向電子郵件轉發服務的適當埠。
