---
description: 控制面板產品需要AdobeClientCare提供的授權。
title: 新增控制面板授權金鑰
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# 新增控制面板授權金鑰{#add-dashboard-license-key}

{{eol}}

控制面板產品需要AdobeClientCare提供的授權。

1. 開啟 **[!UICONTROL SQL Management Studio]** 管理員身分。
1. 開啟由控制面板建立的資料庫（例如thinclientdb）。
1. 以滑鼠右鍵按一下 **[!UICONTROL Configuration]** 表格，按一下 **[!UICONTROL Edit Top 200 Rows]**.
1. 尋找 **[!UICONTROL licenseKey]** 欄位中，並將AdobeClientCare提供的金鑰輸入 **[!UICONTROL Value]** 欄。
1. 重新啟動 **[!UICONTROL Application Pool]** 在 **[!UICONTROL IIS Manager Console]**.
