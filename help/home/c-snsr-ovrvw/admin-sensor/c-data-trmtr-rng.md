---
description: 通過設定警報、檢查感測器的系統狀態等來檢查發射器是否正在運行。
title: 確認資料傳送器執行中
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# 確認資料傳送器執行中{#confirming-that-the-data-transmitter-is-running}

{{eol}}

通過設定警報、檢查感測器的系統狀態等來檢查發射器是否正在運行。

**建議頻率：** 每5-10分鐘

* [檢查傳送程式是否執行中。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [在Insight Server中設定管理警報。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [檢查感測器的系統狀態。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## 檢查傳送器程式 {#section-79806fa3b7034a8eaf571a66e24874d7}

驗證傳送器是否執行的一個方法是檢查 [!DNL Sensor] 傳送器程式在每個 [!DNL Sensor] 已安裝實例。 傳送器程式在Web伺服器的程式清單中顯示為「txlogd」。 您可以使用系統監視工具執行此檢查。

## 在Data Workbench伺服器中設定管理警報 {#section-d98e0f18b8fb45a78419fe75610a3b1e}

驗證傳送器是否執行的另一個方法是在 [!DNL data workbench server]. 設定管理警報後， [!DNL data workbench server] 當未收到來自已設定且先前已連接的資料時，會產生電子郵件警報 [!DNL Sensor] 在 [!DNL Sensor] 中的警報逾時（分鐘）參數 [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] 檔案。 如需設定管理警報的詳細資訊，請參閱 *《伺服器產品安裝與管理指南》*.

## 檢查感測器的系統狀態 {#section-de9d7e359242487a9fbead4ed65aebbc}

要驗證發射器是否正在運行，另一種方法是手動檢查 [!DNL Servers Manager] Data Workbench。

**若要檢視[!DNL Servers Manager]**

* 在Data Workbench中，以滑鼠右鍵按一下工作區中的，按一下 **[!UICONTROL Admin]**，然後在 [!DNL Manage]，按一下 **[!UICONTROL Servers]**.

如果 [!DNL Sensor] 是綠色的，發射器在運行。

如需 [!DNL Servers Manager]，請參閱 *Data Workbench [!DNL Sensor] 指南*.
