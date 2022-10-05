---
description: 有關在Web伺服器上運行一個Web伺服器實例的感測器的一般配置的資訊。
title: 使用一個 Web 伺服器的多個執行個體
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
exl-id: a371f9ed-6c27-4b3d-843f-ae5621013410
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# 使用一個 Web 伺服器的多個執行個體{#working-with-multiple-instances-of-a-web-server}

{{eol}}

有關在Web伺服器上運行一個Web伺服器實例的感測器的一般配置的資訊。

![](assets/web_inst.png)

在此情況下，單個Web伺服器實例正在將資料寫入記憶體映射隊列檔案，該檔案由發送器讀取併發送到 [!DNL data workbench server].

當 [!DNL Sensor] 安裝在運行多個收集器實例的web伺服器上，可以通過以下兩種方式之一進行配置：

* 您可以讓所有收集器模組共用一個佇列檔案。

   使用單個隊列檔案時，管理、配置和管理會有所簡化，因為體系結構本身不那麼複雜。 但是，若使用單一佇列檔案，則無論執行個體數量多寡，整個Web伺服器都會識別為WEB1。

* 您可以多次複製上述架構，並讓每個Web伺服器實例都有一個單獨的隊列檔案。

   這可讓您唯一識別每個Web伺服器執行個體。 換句話說，Web伺服器(以及 [!DNL Sensor] configuration)是此設定的函式。

無論如何，資料仍包含所有主機名稱資訊，以便您能夠區分 [!DNL www.client.com], [!DNL www2.client.com]等。 正確的設定取決於分析目標，以及分析人員是否需要根據在Web伺服器上執行的特定例項來劃分資料。

>[!NOTE]
>
>這類細分通常僅用於操作分析，在該領域之外沒有提供太多實際用途。
