---
description: 在某些情況下，您可能會發現需要將Insight Server電腦新增至現有的Insight Server叢集。
title: 將 Insight Server 新增至現有叢集
uuid: 951bd6fe-14e4-4192-917c-342fde7b43ba
exl-id: 9845c13b-781c-43e9-aaa1-e31418c93ef0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 12%

---

# 將 Insight Server 新增至現有叢集{#adding-insight-servers-to-an-existing-cluster}

{{eol}}

在某些情況下，您可能會發現需要將Insight Server電腦新增至現有的Insight Server叢集。

當您新增 [!DNL Insight Server] DPU或 [!DNL Insight Server] FSU到群集時，必須更新主伺服器上的配置檔案 [!DNL Insight Server] 包括新電腦的地址資訊並設定新DPU或FSU。

>[!NOTE]
>
>本節所述的程式要求 [!DNL Insight]. 如果您尚未安裝 [!DNL Insight]，請遵循* [!DNL Insight] 使用手冊*，再繼續。
