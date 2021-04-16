---
description: 以下是在Data Workbench中安裝工作站（客戶端）的要求和建議。
title: 工作站需求
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# 工作站需求{#workstation-requirements}

以下是在Data Workbench中安裝工作站（客戶端）的要求和建議。

如需其他Data Workbench系統需求，請參閱[伺服器系統需求](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html)。

>[!IMPORTANT]
>
>伺服器、報告伺服器和用戶端元件已升級為可在64位元Windows作業系統上執行。

**開始之前**

在安裝Data Workbench工作站（客戶端）之前，請確保完成以下任務：

* **在Windows** ***2012*** Server中為 *MS System Center端點保護添加排除的處理器，用於* 以下執行檔：

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   這將為這些介面執行檔啟用允許清單權限。

* **安裝Microsoft Excel以匯出分析資料。** 若要將工作區中的資料匯出為Microsoft Excel( [!DNL .xls] 或 [!DNL .xlsx])檔案，您安裝Data Workbench的電腦必須已安裝並註冊Excel。如果Excel尚未註冊，而Data Workbench嘗試首次存取，Excel會顯示註冊對話方塊。 如果您不確定復本是否已註冊，請手動啟動Excel，如果出現註冊對話方塊，請完成註冊程式。

   >[!NOTE]
   >
   >隨著Data Workbench6.4的推出，Excel 2007的支援已中止。 此外，由於Data Workbench僅在Microsoft Windows上針對64位元架構執行，因此建議您也安裝64位元版本的Microsoft Excel。

* **安裝Adobe, [!DNL Acrobat] 將縮放的工作區列印為PDF。** 要將縮放的工作區打印為Adobe PDF格式，安裝Data Workbench的電腦必須安裝 [!DNL Acrobat] Adobe。

* **提供對打印工作區的打印機的訪問。** 要從Data Workbench打印工作區，您安裝Data Workbench的電腦必須具有對打印機的訪問權。Data Workbench可以將工作區列印為彩色或單色印表機，而不需要postscript或其他進階印表機功能。 為獲得最佳結果，Adobe建議使用彩色打印工作區。
* **實施安全措施。** 您應遵循公司針對Data Workbench電腦的一般企業安全政策。為了實現其主要目的，Data Workbench只需要連接到伺服器（通過埠80和443）和任何收集資料的伺服器。 只要您維護Data Workbench軟體並為Data Workbench分配至少10 GB的儲存空間，就可以將Data Workbench硬體用於任何其他用途。
* 要精確呈現視覺效果，您安裝工作台的電腦必須安裝適當的&#x200B;**圖形適配器**（請參閱下面的圖形適配器要求）。

**Data Workbench用戶端需求**

**作業系統**

* Microsoft Windows 7 64位元
* Microsoft Windows 8.1 64位元
* Microsoft Windows 10 64位元

>[!NOTE]
>
>Data Workbench6.1及更新版本不支援Windows XP。

**解析度**

* 必要：1024 x 768(XGA)
* 建議：1920 x 1200(WUXGA)

**圖形適配器**

* 必要：支援OpenGL 3.2的OpenGL硬體加速
* 建議：專用視頻適配器（如NVIDIA或ATI適配器）

**處理器**

* 必要：1.2 GHz或更高的Intel或AMD
* 建議：ICore 2 Duo-Class

**RAM**

* 必要：2 GB
* 建議：4 GB

**連接性**

* 必要：DPU的512 Kbps連結
* 建議：2Mbps或更快的DPU連結

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
