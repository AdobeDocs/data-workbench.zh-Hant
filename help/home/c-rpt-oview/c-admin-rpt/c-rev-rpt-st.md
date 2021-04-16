---
description: 報表伺服器狀態和報表集狀態的相關資訊。
title: 檢閱報表狀態
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# 檢閱報表狀態{#reviewing-report-status}

報表伺服器狀態和報表集狀態的相關資訊。

* [報表伺服器狀態](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [報表集狀態](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## 報表伺服器狀態{#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**建議頻率：僅** 在必要時

[!DNL Report] 每兩分鐘傳送有關伺服器狀態的狀態資訊給資料工作台伺 [!DNL Report] 服器。在[!DNL Detailed Status]介面的[!DNL Report Server Status]節點下可以看到此資訊。

**若要開啟視覺 [!DNL Detailed Status] 化**

1. 在資料工作台中，在工作區中按一下滑鼠右鍵，然後按一下「**[!UICONTROL Admin]** > **[!UICONTROL Servers]**」。

1. 在[!DNL Servers]介面中，按一下右鍵[!DNL Report]電腦連接到的資料工作台伺服器的表徵圖，然後按一下&#x200B;**[!UICONTROL Detailed Status.]**

1. 按一下 **[!UICONTROL Report Server Status]**。

如果有多個[!DNL Report]連接到資料工作台伺服器，則「狀態」向量中會顯示每個[!DNL Report Server]的條目。 通過在[!DNL ReportServer.cfg]檔案的[!DNL Reporting]節點中的「狀態間隔（秒）」參數中指定值，可以覆蓋兩分鐘間隔。

如需[!DNL ReportServer.cfg]檔案的詳細資訊，請參閱[設定報表集](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)。 有關配置[!DNL Report]的資訊，請參見[安裝報告](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91)。

有關[!DNL Detailed Status]的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中的「管理介面」一章。

## 報表集狀態{#section-8569b94266b74a1f85d2a85106a2aaef}

**建議頻率：僅** 在必要時

[!DNL Report] 將每個報表集的狀態資訊傳送至Data Workbench伺服器。基本資訊（例如產生報表集的時間和分發位置）會以綠色文字顯示在報表集上方的資料工作台中。 運行報告時，[!DNL Report]伺服器每兩分鐘輸出一條消息，指示當前查詢的完成百分比。 通過在[!DNL ReportServer.cfg]檔案的[!DNL Reporting]節點中的「完成消息間隔（秒）」參數中指定值，可以覆蓋此兩分鐘間隔。

![](assets/report_status.png)

>[!NOTE]
>
>如果執行報表時發生錯誤，該錯誤會以該報表縮圖下方的紅色文字表示。 您可以以滑鼠右鍵按一下工作區，以顯示完整的錯誤訊息。
