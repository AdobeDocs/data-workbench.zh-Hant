---
description: 使用Data Workbench歷史設定檔，了解配置、硬體和其他變更在一段時間內如何影響效能、穩定性和伺服器容量。
title: Data Workbench 歷史工作區
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
exl-id: e6d7e924-641e-468c-a828-16ebe1c8724f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# Data Workbench 歷史工作區{#data-workbench-historic-workspace}

{{eol}}

使用Data Workbench歷史設定檔，了解配置、硬體和其他變更在一段時間內如何影響效能、穩定性和伺服器容量。

歷史設定檔包含以設定檔為基礎 [設定檔效能](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d) 資料集和伺服器型 [伺服器效能](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09) 資料集 **[!UICONTROL Performance]** 標籤。 以往從Data Workbench伺服器效能的角度檢視的資料集最常使用。 此外，您還可以檢視 [元件](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) 和 [處理模式](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) 選取 **[!UICONTROL Up Time]** 標籤。

![](assets/Historic_Performance.png)

此外，您還可以檢視 [元件](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) 和 [處理模式](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) 選取 **[!UICONTROL Up Time]** 標籤。

如需Data Workbench歷史設定檔中所使用維度的其他參考資訊，請參閱 [Dimension。](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## 設定檔效能工作區 {#section-184a86f9de054970bf68515bb9dea85d}

此資料集包含下列Data Workbench監控的相關量度。

* 每分鐘快速輸入MegaBytes — 在初始日誌處理期間顯示大量資料輸入的度量。
* 每分鐘快速合併MegaBytes — 顯示轉換的度量。

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>若要對您的設定檔進行實際效能評估，請查看速率，而非經過的日曆時間。 此比率以每十分鐘輪詢一次之間的變更值來測量。

## 伺服器效能工作區 {#section-5dad5870384b40e094d50173fcd90a09}

此資料集會監控超出已包含設定檔範圍的伺服器量度，並包含下列Data Workbench監控的相關伺服器量度。

* 估計掃描分鐘數 — 估計查詢解析時間。
* 輪詢延遲毫秒 — 通過測量完成對每個元件的完整服務週期所需的時間來指示軟體繁忙程度。

![](assets/Historic_Server_Performance.png)

## 元件工作區 {#section-5be7223abb384784bafe7b37c764ea66}

此資料集位於「Up Time」（啟動時間）頁簽下。

![](assets/Up_Time.png)

「元件」資料集包含元件運作狀況的兩個方面：

* 通訊量度 — Data Workbench伺服器程式是否回應？
* 所有元件量度 — 在「詳細狀態」頁面的頂端，是主機在Data Workbench伺服器程式內所維護的元件清單。 如果任何元件處於錯誤狀態，則它將列在「錯誤中的元件」(Components in Error)表下。

![](assets/Up_Time_components.png)

## 處理模式工作區 {#section-3e1dedb9474e4b4ba513240943e76817}

此工作區位於Up Time頁簽下。 此工作區可讓您觀察快速輸入、快速合併和即時模式所花費的時間。

![](assets/Up_Time_Processing_mode.png)

此資料集提供重要的伺服器負載特性，例如識別

* 星期幾（例如星期二和星期三的快速輸入率）,
* 小時（在「快速輸入」模式下，一天的百分比是多少？）
