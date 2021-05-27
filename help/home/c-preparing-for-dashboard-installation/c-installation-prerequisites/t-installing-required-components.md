---
description: 安裝所需Microsoft元件的步驟。
title: 安裝必要元件
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# 安裝必要元件{#installing-required-components}

安裝所需Microsoft元件的步驟。

1. 安裝Microsoft .NET Framework v4.0。

   >[!NOTE]
   >
   >只有在安裝和配置IIS Web角色後，才必須安裝此ID。

1. 按照嚮導操作，然後選擇預設值，並在此處提示完成安裝。
1. 安裝後，驗證ASP.NET v.4.0應用程式池已添加到IIS的&#x200B;**[!UICONTROL Application Pools]**&#x200B;清單中。
1. 安裝Microsoft SQL Server資料庫。

   使用管理工具使用任何版本的SQL Server 2008或2008 R2（支援Express）(Adobe建議使用SQL Server 2008 R2 SP1 - Express Edition)。 1.對於未提前運行現有SQL Server實例的常規安裝，請在&#x200B;**[!UICONTROL Instance Configuration]**&#x200B;螢幕上選擇&#x200B;**[!UICONTROL Default Instance]**&#x200B;選項。
1. 對於其餘的配置選項，在提示完成安裝時，請遵循嚮導並選擇預設值。
1. 安裝Microsoft Web Deploy v2.0。

   對於大多數安裝，**[!UICONTROL Typical]**&#x200B;安裝是正常的。 但是，如果您計畫執行遠程部署，則需要完整安裝（選擇&#x200B;**[!UICONTROL Complete]**）。

   正確安裝所有必要條件後，您就可以準備Data Workbench伺服器以與控制面板通訊。
