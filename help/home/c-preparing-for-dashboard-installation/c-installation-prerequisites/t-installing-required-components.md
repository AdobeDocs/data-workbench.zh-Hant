---
description: 安裝所需Microsoft元件的步驟。
solution: Analytics
title: 安裝所需元件
topic: Data workbench
uuid: e23fba09-4684-4daf-8426-ea91169b3348
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安裝所需元件{#installing-required-components}

安裝所需Microsoft元件的步驟。

1. 安裝Microsoft .NET Framework v4.0。

   >[!NOTE]
   >
   >必須在安裝和配置IIS Web角色後才安裝此程式。

1. 按照嚮導操作，並選擇提示完成安裝的預設設定。
1. 安裝後，驗證IIS中的清單中是否添加了ASP.NET v.4.0 **[!UICONTROL Application Pools]** 應用程式池。
1. 安裝Microsoft SQL Server資料庫。

   使用任何版本的SQL Server 2008或2008 R2（支援Express）和管理工具（Adobe建議使用SQL Server 2008 R2 SP1 - Express Edition）。 1.對於沒有提前運行的現有SQL Server實例的常規安裝，請在螢幕上 **[!UICONTROL Default Instance]** 選擇該選 **[!UICONTROL Instance Configuration]** 項。
1. 對於其餘的配置選項，請遵循嚮導，並在提示完成安裝時選擇預設值。
1. 安裝Microsoft Web Deploy v2.0。

   對於大多數安裝，安 **[!UICONTROL Typical]** 裝都正常。 但是，如果您打算執行遠程部署，則需要完整安裝(選擇 **[!UICONTROL Complete]**)。

   在正確安裝所有必要條件後，您就可準備資料工作台伺服器以與控制面板通訊。
