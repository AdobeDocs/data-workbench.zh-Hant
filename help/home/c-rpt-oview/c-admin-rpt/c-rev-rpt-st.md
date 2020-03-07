---
description: 報表伺服器狀態和報表集狀態的相關資訊。
solution: Analytics
title: 複查報表狀態
topic: Data workbench
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 複查報表狀態{#reviewing-report-status}

報表伺服器狀態和報表集狀態的相關資訊。

* [報表伺服器狀態](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [報表集狀態](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## 報表伺服器狀態 {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**建議頻率：** 僅在需要時

[!DNL Report] 每兩分鐘傳送有關伺服器狀態的狀態資訊給資料工作台伺 [!DNL Report] 服器。 此資訊可在介面的節 [!DNL Report Server Status] 點下查 [!DNL Detailed Status] 看。

**若要開啟視覺[!DNL Detailed Status]化**

1. 在資料工作台中，在工作區中按一下滑鼠右鍵，然後按一下 **[!UICONTROL Admin]** > **[!UICONTROL Servers]**。

1. 在介面 [!DNL Servers] 中，以滑鼠右鍵按一下電腦所連接之資料工作台伺服器的 [!DNL Report] 圖示，然後按一下 **[!UICONTROL Detailed Status.]**

1. 按一下 **[!UICONTROL Report Server Status]**.

如果有多個連 [!DNL Report] 接至資料工作台伺服器，「狀態」向量中會顯示每 [!DNL Report Server] 個伺服器的項目。 通過在檔案節點的「狀態間隔（秒）」參數中指定值，可以覆蓋兩分 [!DNL Reporting] 鐘的間 [!DNL ReportServer.cfg] 隔。

如需檔案的詳 [!DNL ReportServer.cfg] 細資訊，請 [參閱設定報表集](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)。 如需設定的詳細資 [!DNL Report]訊，請 [參閱安裝報表](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91)。

如需詳細資訊， [!DNL Detailed Status]請參閱資料工作台使用指南的「管 *理介面」一章*。

## 報表集狀態 {#section-8569b94266b74a1f85d2a85106a2aaef}

**建議頻率：** 僅在需要時

[!DNL Report] 將每個報表集的狀態資訊傳送至資料工作台伺服器。 基本資訊（例如產生報表集的時間和分發位置）會以綠色文字顯示在報表集上方的資料工作台中。 執行報表時， [!DNL Report] 伺服器會每兩分鐘輸出一則訊息，指出目前查詢的完成百分比。 通過在檔案節點的「完成消息間隔（秒）」參數中指定值，可以覆蓋此兩分 [!DNL Reporting] 鐘的間 [!DNL ReportServer.cfg] 隔。

![](assets/report_status.png)

>[!NOTE]
>
>如果執行報表時發生錯誤，該錯誤會以該報表縮圖下方的紅色文字表示。 您可以以滑鼠右鍵按一下工作區，以顯示完整的錯誤訊息。

