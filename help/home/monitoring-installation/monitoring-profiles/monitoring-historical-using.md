---
description: 使用資料工作台歷史設定檔，瞭解配置、硬體和其他變更如何影響效能、穩定性和伺服器容量。
title: Data Workbench 歷史工作區
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
exl-id: e6d7e924-641e-468c-a828-16ebe1c8724f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# Data Workbench 歷史工作區{#data-workbench-historic-workspace}

使用資料工作台歷史設定檔，瞭解配置、硬體和其他變更如何影響效能、穩定性和伺服器容量。

「歷史」配置檔案包括基於配置檔案的[Profile Performance](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d)資料集和&#x200B;**[!UICONTROL Performance]**&#x200B;頁籤下基於伺服器的[Server Performance](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09)資料集。 這些是過去從資料工作台伺服器效能的角度檢視的最常用資料集。 此外，您還可以選擇&#x200B;**[!UICONTROL Up Time]**&#x200B;標籤來查看[元件](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)和[處理模式](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)。

![](assets/Historic_Performance.png)

此外，您還可以選擇&#x200B;**[!UICONTROL Up Time]**&#x200B;標籤來查看[元件](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)和[處理模式](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)。

如需有關資料工作台歷史資料中使用的維度的其他參考資訊，請參閱「分析歷史資料」中的「Dimension」。](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)[

## 配置檔案效能工作區{#section-184a86f9de054970bf68515bb9dea85d}

此資料集包含下列資料工作台監控的相關度量。

* 每分鐘快速輸入MegaBytes —— 顯示初始記錄處理期間大量資料輸入的量度。
* 每分鐘快速合併MegaBytes —— 顯示轉換的量度。

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>若要對您的個人檔案進行實際效能評估，請查看比率，而非經過的日曆時間。 速率是以每10分鐘輪詢一次的更改值來測量。

## 伺服器效能工作區{#section-5dad5870384b40e094d50173fcd90a09}

此資料集會監控超出所包含描述檔範圍的伺服器量度，並包含下列相關的伺服器量度以進行資料工作台監控。

* 估計掃描分鐘數— 估計查詢解析度時間。
* 輪詢延遲毫秒— 測量完成每個元件的完整服務週期所需的時間，以指出軟體有多忙。

![](assets/Historic_Server_Performance.png)

## 元件工作區{#section-5be7223abb384784bafe7b37c764ea66}

此資料集位於「啟動時間」標籤下。

![](assets/Up_Time.png)

Components資料集包含兩個方面的元件健康：

* 通訊量度— 資料工作台伺服器程式是否回應？
* 所有元件量度— 在「詳細狀態」頁的頂部是主機在資料工作台伺服器進程中服務的元件清單。 如果任何元件處於錯誤狀態，則它將列在「錯誤中的元件」(Components in Error)表格下。

![](assets/Up_Time_components.png)

## 處理模式工作區{#section-3e1dedb9474e4b4ba513240943e76817}

此工作區位於「Up Time」（啟動時間）頁籤下。 此工作區可讓您觀察快速輸入、快速合併和即時模式所花的時間。

![](assets/Up_Time_Processing_mode.png)

此資料集提供重要的伺服器負載特性，例如識別

* 星期幾（例如星期二和星期三的快速輸入率）,
* 一天中的某小時（在「快速輸入」模式下該天的百分比是多少？）
