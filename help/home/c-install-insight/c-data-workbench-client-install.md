---
description: 以下是以Data Workbench安裝工作站（用戶端）的需求和建議。
title: 工作站需求
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# 工作站需求{#workstation-requirements}

以下是以Data Workbench安裝工作站（用戶端）的需求和建議。

有關其他Data Workbench系統要求，請參閱[伺服器系統要求](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html)。

>[!IMPORTANT]
>
>伺服器、報表伺服器和用戶端元件已升級，可在64位元Windows作業系統上執行。

**開始之前**

安裝Data Workbench工作站（客戶端）之前，請確定您已完成這些任務：

* **** ***Windows 2012*** 伺服 *器中MS System Center端點保護的AddExcludedProcesss，適用* 於下列執行檔：

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   這將為這些介面執行檔啟用允許清單權限。

* **安裝Microsoft Excel以匯出分析資料。** 若要將資料從工作區匯出為Microsoft Excel( [!DNL .xls] 或 [!DNL .xlsx])檔案，您安裝Data Workbench的電腦必須安裝並註冊Excel。如果Excel尚未註冊，且Data Workbench嘗試首次存取，則Excel會顯示註冊對話方塊。 如果您不確定副本是否已註冊，請手動啟動Excel，如果出現註冊對話框，請完成註冊過程。

   >[!NOTE]
   >
   >隨著Data Workbench6.4的發行，Excel 2007的支援已停止。 此外，由於Data Workbench只在Microsoft Windows上執行64位架構，因此建議您同時安裝64位版的Microsoft Excel。

* **安裝Adobe, [!DNL Acrobat] 以將縮放的工作區列印為PDF。** 若要將縮放的工作區打印為Adobe PDF格式，您安裝Data Workbench的電腦必須安裝 [!DNL Acrobat] Adobe。

* **提供對打印工作區的打印機的訪問。** 要從Data Workbench打印工作區，安裝Data Workbench的電腦必須具有打印機的訪問權限。Data Workbench可將工作區打印為彩色或單色打印機，並且不需要postscript或其他高級打印機功能。 為獲得最佳結果，Adobe建議以顏色打印工作區。
* **實施安全措施。** 您應該遵循公司針對Data Workbench電腦的一般企業安全政策。為了滿足其主要目的，Data Workbench只需要連接到伺服器（通過埠80和443）以及任何收集資料的伺服器的能力。 只要您維護Data Workbench軟體，並為Data Workbench分配至少10 GB的儲存空間，就可以將Data Workbench硬體用於任何其他用途。
* 若要準確呈現視覺效果，安裝工作台的電腦必須安裝適當的&#x200B;**圖形適配器**（請參閱下面的圖形適配器要求）。

**Data Workbench用戶端需求**

**作業系統**

* Microsoft Windows 7 64位
* Microsoft Windows 8.1 64位
* Microsoft Windows 10 64位

>[!NOTE]
>
>Data Workbench6.1及更新版本不支援Windows XP。

**解析度**

* 必要：1024 x 768(XGA)
* 建議：1920 x 1200(WUXGA)

**圖形適配器**

* 必要：支援OpenGL 3.2的OpenGL硬體加速
* 建議：專用視頻適配器（例如NVIDIA或ATI適配器）

**處理器**

* 必要：1.2 GHz或更高的Intel或AMD
* 建議：ICore 2雙核級

**RAM**

* 必要：2 GB
* 建議：4 GB

**連接**

* 必要：到DPU的512 Kbps鏈路
* 建議：2Mbps或更快的DPU鏈路

**檔案系統**

NTFS

**磁碟儲存**

至少十(10)GB或更高的可用硬碟空間

**打印**

用於打印工作區和報告的打印機訪問（彩色或灰階打印機）

**其他**

* 專用滑鼠
* 低眩光工作環境
* 遮光面顯示器
