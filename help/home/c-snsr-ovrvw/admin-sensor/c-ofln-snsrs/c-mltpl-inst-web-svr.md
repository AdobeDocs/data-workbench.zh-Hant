---
description: 有關感測器在Web伺服器上運行一個Web伺服器實例時的一般配置的資訊。
solution: Analytics
title: 使用一個 Web 伺服器的多個執行個體
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---


# 使用一個 Web 伺服器的多個執行個體{#working-with-multiple-instances-of-a-web-server}

有關感測器在Web伺服器上運行一個Web伺服器實例時的一般配置的資訊。

![](assets/web_inst.png)

在這種情況下，單個Web伺服器實例正在將資料寫入記憶體映射隊列檔案，該檔案由發射器讀取併發送到 [!DNL data workbench server]。

當安 [!DNL Sensor] 裝在運行多個收集器實例的Web伺服器上時，可以通過以下兩種方式之一進行配置：

* 您可以讓所有收集器模組共用一個隊列檔案。

   使用單一佇列檔案時，由於架構本身較不複雜，所以管理、設定和管理會略有簡化。 不過，使用單一佇列檔案時，不論執行個體數目為何，整個Web伺服器都會識別為WEB1。

* 您可以多次複製上述架構，並讓每個Web伺服器實例都具有單獨的隊列檔案。

   這可讓您唯一識別每個Web伺服器實例。 換句話說，Web伺服器的標識（以及配置中相應的感測器ID） [!DNL Sensor] 是此配置的功能。

無論如何，資料仍包含所有主機名稱資訊，以便您能夠區 [!DNL www.client.com]分 [!DNL www2.client.com]、等等。 正確的設定由分析目標以及分析人員是否需要根據在Web伺服器上執行的特定例項來分段資料來決定。

>[!NOTE]
>
>這種分段通常僅用於操作分析，在該區域之外不提供很多實際用途。

