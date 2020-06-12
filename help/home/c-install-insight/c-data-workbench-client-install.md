---
description: 以下是在資料工作台中安裝工作站（客戶端）的要求和建議。
solution: Analytics
title: 工作站需求
topic: Data workbench
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
translation-type: tm+mt
source-git-commit: 2930bd3ae06e700e75144221fc993efdd6bd1e85
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 1%

---


# 工作站需求{#workstation-requirements}

以下是在資料工作台中安裝工作站（客戶端）的要求和建議。

如需其 [他資料工作台系統需求](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html) ，請參閱伺服器系統需求。

>[!IMPORTANT]
>
>伺服器、報告伺服器和用戶端元件已升級為可在64位元Windows作業系統上執行。

**開始之前**

在安裝資料工作台工作站（客戶端）之前，請確保完成了以下任務：

* **在Windows** 2012 ***伺服器中為*** MS System Center端點保護添加排除的進程，以用於以下執行檔 ** :

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   這將為這些介面執行檔啟用允許清單權限。

* **安裝Microsoft Excel以匯出分析資料。** 若要將工作區中的資料匯出為Microsoft Excel( [!DNL .xls] 或 [!DNL .xlsx])檔案，您安裝資料工作台的電腦必須已安裝並註冊Excel。 如果Excel尚未註冊，而「資料工作台」嘗試首次存取，Excel會顯示註冊對話方塊。 如果您不確定復本是否已註冊，請手動啟動Excel，如果出現註冊對話方塊，請完成註冊程式。

   >[!NOTE]
   >
   >隨著Data Workbench 6.4的推出，Excel 2007的支援已中止。 此外，由於資料工作台僅在Microsoft Windows 64位元架構上執行，因此建議您也安裝64位元版本的Microsoft Excel。

* **安裝Adobe[!DNL Acrobat]以將縮放的工作區列印為PDF。** 若要將縮放的工作區列印為Adobe PDF格式，您安裝資料工作台的電腦必須安裝Adobe [!DNL Acrobat] PDF。

* **提供對打印工作區的打印機的訪問。** 若要從資料工作台列印工作區，您安裝資料工作台的電腦必須擁有印表機的存取權。 資料工作台可將工作區列印至彩色或單色印表機，而不需要postscript或其他進階印表機功能。 為獲得最佳結果，Adobe建議以色彩列印工作區。
* **實施安全措施。** 您應遵循公司針對資料工作台電腦的一般企業安全性政策。 為滿足其主要用途，資料工作台只需要連接至伺服器（透過埠80和443）以及任何收集資料的伺服器。 只要您維護「資料工作台」軟體，並為「資料工作台」分配至少10 GB的儲存空間，您就可將「資料工作台」硬體用於任何其他用途。
* 若要精確呈現視覺效果，您安裝工作台的電腦必須安裝適當的圖形 **適配器** （請參閱下方的圖形適配器需求）。

**資料工作台用戶端需求**

**作業系統**

* Microsoft Windows 7 64位元
* Microsoft Windows 8.1 64位元
* Microsoft Windows 10 64位元

>[!NOTE]
>
>Data Workbench 6.1及更新版本不支援Windows XP。

**解析度**

* 必要： 1024 x 768(XGA)
* 建議： 1920 x 1200(WUXGA)

**圖形適配器**

* 必要： 支援OpenGL 3.2的OpenGL硬體加速
* 建議： 專用視頻適配器（如NVIDIA或ATI適配器）

**處理器**

* 必要： 1.2 GHz或更高的Intel或AMD
* 建議： ICore 2 Duo-Class

**RAM**

* 必要： 2 GB
* 建議： 4 GB

**連接性**

* 必要： DPU的512 Kbps連結
* 建議： 2Mbps或更快的DPU連結

**檔案系統**

NTFS

**磁碟儲存**

至少有十(10)GB或更大的可用硬碟空間

**列印**

列印工作區和報表的印表機存取（彩色或灰階印表機）

**其他**

* 專用滑鼠
* 低眩光工作環境
* 遮光面顯示器

