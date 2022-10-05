---
description: 「設定」選項會開啟Insight.cfg檔案，此檔案會控制您與各種伺服器的連線。
title: 組態選項
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---

# 組態選項{#configuration-option}

{{eol}}

「設定」選項會開啟Insight.cfg檔案，此檔案會控制您與各種伺服器的連線。

![](assets/cfg_Workstation.png)

**若要編輯Insight.cfg檔案**

1. 在 [!DNL Insight.cfg] 視需要修改參數。 如需 [!DNL Insight.cfg] 檔案，請參閱 [分析設定參數](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. 若要儲存配置設定，請按一下右鍵 **[!UICONTROL Insight.cfg (modified)]** 在視窗頂端按一下 **[!UICONTROL Save as Insight.cfg]**.

**添加新伺服器**

1. 在 [!DNL Insight.cfg] 窗口，按一下右鍵 **[!UICONTROL Servers]** 按一下 **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. 完成或修改伺服器參數以讓Data Workbench能夠存取所需的伺服器。 如需 [!DNL Insight.cfg] 檔案，請參閱 [分析設定參數](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. 對要配置連接的每台伺服器重複步驟1和步驟2。
1. 若要儲存配置設定，請按一下右鍵 **[!UICONTROL Insight.cfg (modified)]** 在視窗頂端按一下 **[!UICONTROL Save as Insight.cfg]**.

Data Workbench嘗試使用您指定的設定連接到伺服器。 如果已建立連線，綠色節點會顯示在 [!DNL Servers Manager] 如下所示。 如果Data Workbench無法連線至伺服器，則會顯示紅色節點。

![](assets/vis_SysStat_RedGreenDots.png)
