---
description: 報表伺服器狀態和報表集狀態的相關資訊。
title: 檢閱報表狀態
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# 檢閱報表狀態{#reviewing-report-status}

{{eol}}

報表伺服器狀態和報表集狀態的相關資訊。

* [報表伺服器狀態](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [報表集狀態](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## 報表伺服器狀態 {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**建議頻率：** 僅在必要時

[!DNL Report] 每兩分鐘傳送狀態資訊至data workbench伺服器，了解 [!DNL Report] 伺服器。 此資訊可在 [!DNL Report Server Status] 節點 [!DNL Detailed Status] 介面。

**若要開啟 [!DNL Detailed Status] 視覺效果**

1. 在Data Workbench中，以滑鼠右鍵按一下工作區中的，然後按一下 **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. 在 [!DNL Servers] 介面中，以滑鼠右鍵按一下資料工作台伺服器的圖示， [!DNL Report] 電腦連接到並按一下 **[!UICONTROL Detailed Status.]**

1. 按一下 **[!UICONTROL Report Server Status]**。

若有多個 [!DNL Report] 連線至data workbench伺服器時，每個伺服器都會顯示項目 [!DNL Report Server] 在狀態向量中。 您可以在 [!DNL Reporting] 節點 [!DNL ReportServer.cfg] 檔案。

如需 [!DNL ReportServer.cfg] 檔案，請參閱 [設定報表集](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). 如需設定的相關資訊 [!DNL Report]，請參閱 [安裝報表](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

如需 [!DNL Detailed Status]，請參閱 *Data Workbench使用手冊*.

## 報表集狀態 {#section-8569b94266b74a1f85d2a85106a2aaef}

**建議頻率：** 僅在必要時

[!DNL Report] 將每個報告集的狀態資訊發送到Data Workbench伺服器。 基本資訊（例如產生報表集時和分送報表集的位置）會以綠色文字顯示在報表集上方的Data Workbench中。 執行報表時， [!DNL Report] 伺服器每兩分鐘輸出一條消息，指示當前查詢的完成百分比。 可以在以下欄位中的Completion Message Interval（秒）參數中指定值，以覆寫此兩分鐘間隔： [!DNL Reporting] 節點 [!DNL ReportServer.cfg] 檔案。

![](assets/report_status.png)

>[!NOTE]
>
>如果執行報表時發生錯誤，該錯誤會以該報表縮圖下方的紅色文字表示。 您可以以滑鼠右鍵按一下工作區，以顯示完整錯誤訊息。
