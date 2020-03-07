---
description: 存取控制設定檔案Access Control.cfg定義存取控制群組，Insight Server會根據傳入連線憑證的屬性（OU、CN等）授予檔案權限。
solution: Insight
title: 配置訪問控制
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置訪問控制{#configuring-access-control}

存取控制設定檔案Access Control.cfg定義存取控制群組，Insight Server會根據傳入連線憑證的屬性（OU、CN等）授予檔案權限。

**建議頻率：** 視需要

[!DNL Insight Server] 提供可配置的訪問控制組以管理到的連接的安全 [!DNL Insight Server]性。 存取控制群組會識別允許透過執行管理功能的使用者 [!DNL Insight]。

如果需要為新用戶或新電腦提供訪問權，例如在將電腦添加到群集時，只需編 [!DNL Insight Server] 輯訪問控制配置檔案。
