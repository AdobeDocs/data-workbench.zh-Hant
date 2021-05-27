---
description: 將感測器安裝在要測量其活動的伺服器上。
title: 安裝 Sensor
uuid: 8d500fd0-daa0-453b-8284-b3f112a358ce
exl-id: cd5b54bf-301a-41a9-a69c-d9adb314be03
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 2%

---

# 安裝 Sensor{#installing-sensor}

將感測器安裝在要測量其活動的伺服器上。

要從中捕獲事件資料的每台伺服器必須運行[!DNL Sensor]。

[!DNL Sensor] 可以安裝在各種支援的web和應用程式伺服器上，或安裝在專門的資料收集伺服器上，這些資料收集伺服器用於從已被標籤為要測量的頁面、廣告和其他Internet對象獲取資訊。

>[!NOTE]
>
>[!DNL Sensor] 不會降低正確配置的web 、應用程式或資料收集伺服器的效能。

Adobe設計了[!DNL Sensor] ，以支援不斷壯大的Web和J2EE應用程式伺服器系列，包括但不限於AOLServer、Apache、iPlanet、JBoss、Microsoft IIS、Netscape Enterprise、Tomcat和Weblogic，這些伺服器在常用作業系統上運行，包括但不限於Microsoft Windows、AIX、Linux和Solaris。 [!DNL Sensor’s] 模組化體系結構使Adobe能夠根據需要為其他應用程式快速建立新的資料獲取邏輯。

本章包含為Web伺服器/作業系統組合安裝[!DNL Sensor]的過程。

如果尚未安裝從[!DNL Sensor]收集資料的[!DNL data workbench server]，則必須先安裝，然後才能執行本章中的過程。
