---
description: 通過設定警報、檢查感測器的系統狀態等來檢查發射器是否正在運行。
title: 確認資料傳送器執行中
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# 確認資料傳送器執行中{#confirming-that-the-data-transmitter-is-running}

通過設定警報、檢查感測器的系統狀態等來檢查發射器是否正在運行。

**建議頻率：** 每5-10分鐘

* [檢查傳送程式是否執行中。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [在Insight Server中設定管理警報。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [檢查感測器的系統狀態。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## 檢查發射器進程{#section-79806fa3b7034a8eaf571a66e24874d7}

驗證傳輸器是否正在運行的一個方法是檢查[!DNL Sensor]傳輸器進程是否在安裝[!DNL Sensor]實例的每個Web伺服器上運行。 傳送器程式在Web伺服器的程式清單中顯示為「txlogd」。 您可以使用系統監視工具執行此檢查。

## 在Data Workbench伺服器{#section-d98e0f18b8fb45a78419fe75610a3b1e}中設定管理警報

驗證傳輸器是否正在運行的另一種方法是在[!DNL data workbench server]中設定自動管理警報。 配置管理警報後，[!DNL data workbench server]在[!DNL data workbench server’s] [!DNL Administrative Alerts.cfg]檔案的[!DNL Sensor]警報超時(min)參數中指定的時間範圍內未收到已配置且先前連接的[!DNL Sensor]的資料時，生成電子郵件警報。 有關設定管理警報的詳細資訊，請參閱&#x200B;*伺服器產品安裝和管理指南*。

## 檢查感測器{#section-de9d7e359242487a9fbead4ed65aebbc}的系統狀態

驗證傳輸器是否正在運行的另一種方法是手動檢查Data Workbench中的[!DNL Servers Manager]。

**若要檢視[!DNL Servers Manager]**

* 在「Data Workbench」中，按一下右鍵工作區中的&#x200B;**[!UICONTROL Admin]**，然後按一下[!DNL Manage]下方的&#x200B;**[!UICONTROL Servers]**。

如果[!DNL Sensor]的圖示為綠色，則傳輸器正在執行。

有關[!DNL Servers Manager]的詳細資訊，請參閱&#x200B;*Data Workbench[!DNL Sensor]指南*&#x200B;的管理介面一章。
