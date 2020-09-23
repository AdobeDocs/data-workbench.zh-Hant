---
description: 通過設定警報、檢查感測器的系統狀態等來檢查發射器是否正在運行。
solution: Analytics
title: 確認資料傳送器執行中
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---


# 確認資料傳送器執行中{#confirming-that-the-data-transmitter-is-running}

通過設定警報、檢查感測器的系統狀態等來檢查發射器是否正在運行。

**建議頻率：** 每5-10分鐘

* [檢查發射器進程是否正在運行。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [在Insight Server中設定管理警報。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [檢查感測器的系統狀態。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## 檢查發射器進程 {#section-79806fa3b7034a8eaf571a66e24874d7}

驗證發射器是否正在運行的一種方法是檢查在安裝實例的 [!DNL Sensor] 每個Web伺服器上是否運行 [!DNL Sensor] 發射器進程。 傳送器程式會在Web伺服器的程式清單中顯示為「txlogd」。 您可以使用系統監控工具執行此檢查。

## 在資料工作台伺服器中設定管理警報 {#section-d98e0f18b8fb45a78419fe75610a3b1e}

另一個驗證發射器是否正在運行的方法是在中設定自動管理警報 [!DNL data workbench server]。 當管理警報已配置時，當 [!DNL data workbench server] Alert Timeout(min)參數中指定的時間範圍內未收到已配置和先前連接的資料時， [!DNL Sensor] The [!DNL Sensor] Email Alert [!DNL data workbench server’s] Temout(min)將生成電子郵件警 [!DNL Administrative Alerts.cfg] 報。 有關設定管理警報的詳細資訊，請參 *閱伺服器產品安裝和管理指南*。

## 檢查感測器的系統狀態 {#section-de9d7e359242487a9fbead4ed65aebbc}

另一個驗證傳送器是否正在執行的方式是手動檢查「資 [!DNL Servers Manager] 料工作台」。

**若要檢視[!DNL Servers Manager]**

* 在「資料工作台」中，在工作區內按一下滑鼠右鍵，按一 **[!UICONTROL Admin]**&#x200B;下，然後按 [!DNL Manage]一下，再按 **[!UICONTROL Servers]**。

如果表徵圖為 [!DNL Sensor] 綠色，則發射器正在運行。

如需有關的詳細資 [!DNL Servers Manager]訊，請參閱資料工作台指南的「管 *理介面[!DNL Sensor]」一章*。
