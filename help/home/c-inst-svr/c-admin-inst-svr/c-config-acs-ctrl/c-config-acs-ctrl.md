---
description: Access Control配置檔案Access Control.cfg定義了訪問控制組，Insight Server通過這些組根據傳入連接證書的屬性（OU、CN等）授予檔案的權限。
title: 設定存取控制
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# 設定存取控制{#configuring-access-control}

{{eol}}

Access Control配置檔案Access Control.cfg定義了訪問控制組，Insight Server通過這些組根據傳入連接證書的屬性（OU、CN等）授予檔案的權限。

**建議頻率：** 視需要

[!DNL Insight Server] 提供可配置的訪問控制組，以管理連接的安全性 [!DNL Insight Server]. 訪問控制組標識允許通過 [!DNL Insight].

如果您需要提供新使用者或新電腦的存取權，例如將電腦新增至 [!DNL Insight Server] 群集，只需編輯Access Control配置檔案。
