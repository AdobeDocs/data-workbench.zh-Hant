---
description: 控制面板產品需要AdobeClientCare提供的授權。
title: 新增控制面板授權金鑰
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# 新增控制面板授權金鑰{#add-dashboard-license-key}

控制面板產品需要AdobeClientCare提供的授權。

1. 以管理員身分開啟&#x200B;**[!UICONTROL SQL Management Studio]**。
1. 開啟由控制面板建立的資料庫（例如thinclientdb）。
1. 按一下右鍵&#x200B;**[!UICONTROL Configuration]**&#x200B;表，然後按一下&#x200B;**[!UICONTROL Edit Top 200 Rows]**。
1. 查找&#x200B;**[!UICONTROL licenseKey]**&#x200B;欄位，並在&#x200B;**[!UICONTROL Value]**&#x200B;列中輸入由AdobeClientCare提供的鍵。
1. 在&#x200B;**[!UICONTROL IIS Manager Console]**&#x200B;中重新啟動&#x200B;**[!UICONTROL Application Pool]**。
