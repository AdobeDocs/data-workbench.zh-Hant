---
description: 若要讓報表伺服器的某些功能運作，您必須先提供並設定硬體或軟體，才能安裝。
solution: Analytics
title: 開始之前
topic: Data workbench
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# 開始之前{#before-you-begin}

若要讓報表伺服器的某些功能運作，您必須先提供並設定硬體或軟體，才能安裝。

## 基本報表伺服器需求 {#section-e891eaee79fe4fa98e658426dc3b2777}

輸出的報表可以是。PNG影像或。XLS試算表格式，也可以是電子郵件格式。 硬體需求與資料工作台用 [戶端相同](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements)。

報表伺服器有下列需求：

* 存取檔案系統以輸出資料（網路共用或本機磁碟機）。
* 訪問已配置的SMTP伺服器。
* Microsoft Excel 2010 64位元或更高版本已安裝在伺 [!DNL Report] 服器上。 如需 [詳細資訊，請參閱Office伺服器端自動化注意事項](http://support.microsoft.com/kb/257757) 。

## 其他需求 {#section-f53d4388656a4dfc90aefe29dfabef89}

* **安裝適當的圖形適配器。** 要正確呈現報告，安裝 [!DNL Report] Server的電腦必須安裝適當的圖形適配器。

* **安裝Microsoft Excel以產生Excel檔案的報表。** 若要以Microsoft Excel檔案(或 [!DNL .xls][!DNL .xlsx])產生和分發報表，您安裝Report Server的機器必須安裝並註冊適當版本的64位元Microsoft Excel。 如果Excel尚未註冊，而報表伺服器嘗試首次存取，Excel將顯示註冊對話方塊。 如果您不確定復本是否已註冊，請手動啟動Excel，如果出現註冊對話方塊，請完成註冊程式。

   >[!NOTE]
   >
   >當您以Excel檔案產生報表時，會開啟新的Excel例項。 如需此程式的詳細資訊，請參閱 [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757)。

* **提供對SMTP伺服器的訪問權，以通過電子郵件分發報告。** 如果要以電子郵件發送報告，報告伺服器必須能夠連接到SMTP伺服器，並且必須開啟電子郵件轉發服務的相應埠。

