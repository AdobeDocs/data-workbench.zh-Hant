---
description: 「設定」選項會開啟您的Insight.cfg檔案，此檔案會控制您與各種伺服器的連線。
title: 組態選項
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---

# 組態選項{#configuration-option}

「設定」選項會開啟您的Insight.cfg檔案，此檔案會控制您與各種伺服器的連線。

![](assets/cfg_Workstation.png)

**若要編輯Insight.cfg檔案**

1. 在[!DNL Insight.cfg]視窗中，視需要修改參數。 如需[!DNL Insight.cfg]檔案中參數的詳細說明，請參閱[Insight Configuration Parameters](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。
1. 要保存配置設定，請按一下右鍵窗口頂部的&#x200B;**[!UICONTROL Insight.cfg (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save as Insight.cfg]**。

**若要新增伺服器**

1. 在[!DNL Insight.cfg]視窗中，以滑鼠右鍵按一下&#x200B;**[!UICONTROL Servers]**，然後按一下&#x200B;**[!UICONTROL Add new child]** > **[!UICONTROL Server]**。

   ![](assets/cfg_Workstation_AddServer.png)

1. 完成或修改伺服器參數，以便Data Workbench訪問所需的伺服器。 如需[!DNL Insight.cfg]檔案中參數的詳細說明，請參閱[Insight Configuration Parameters](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。
1. 對要配置連接的每台伺服器重複步驟1和步驟2。
1. 要保存配置設定，請按一下右鍵窗口頂部的&#x200B;**[!UICONTROL Insight.cfg (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save as Insight.cfg]**。

Data Workbench嘗試使用您指定的設定連接到伺服器。 如果建立連接，[!DNL Servers Manager]中將顯示綠色節點，如下所示。 如果Data Workbench無法連接到伺服器，則會顯示一個紅色節點。

![](assets/vis_SysStat_RedGreenDots.png)
