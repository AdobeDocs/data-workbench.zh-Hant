---
description: Access Control配置檔案Access Control.cfg定義了訪問控制組，Insight Server通過這些組根據傳入連接證書的屬性（OU、CN等）授予檔案的權限。
title: 設定存取控制
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# 設定存取控制{#configuring-access-control}

Access Control配置檔案Access Control.cfg定義了訪問控制組，Insight Server通過這些組根據傳入連接證書的屬性（OU、CN等）授予檔案的權限。

**建議頻率：** 視需要

[!DNL Insight Server] 提供可配置的訪問控制組以管理到的連接的安 [!DNL Insight Server]全性。訪問控制組標識允許通過[!DNL Insight]執行管理功能的用戶。

如果需要為新用戶或新電腦提供訪問權限，例如在將電腦添加到[!DNL Insight Server]群集時，只需編輯訪問控制配置檔案即可。
