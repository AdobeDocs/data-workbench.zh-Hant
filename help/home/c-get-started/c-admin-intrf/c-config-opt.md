---
description: 「設定」選項會開啟您的Insight.cfg檔案，此檔案會控制您與各種伺服器的連線。
solution: Analytics
title: 配置選項
topic: Data workbench
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置選項{#configuration-option}

「設定」選項會開啟您的Insight.cfg檔案，此檔案會控制您與各種伺服器的連線。

![](assets/cfg_Workstation.png)

**若要編輯Insight.cfg檔案**

1. 在窗口 [!DNL Insight.cfg] 中，根據需要修改參數。 如需檔案中參數的詳細說明，請 [!DNL Insight.cfg] 參閱Insight設定 [參數](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。
1. 要保存配置設定，請按一下右鍵 **[!UICONTROL Insight.cfg (modified)]** 窗口頂部的，然後按一下 **[!UICONTROL Save as Insight.cfg]**。

**若要新增伺服器**

1. 在視窗 [!DNL Insight.cfg] 中，以滑鼠右鍵按一 **[!UICONTROL Servers]** 下並按 **[!UICONTROL Add new child]** > **[!UICONTROL Server]**。

   ![](assets/cfg_Workstation_AddServer.png)

1. 完成或修改伺服器參數，讓資料工作台可存取所需的伺服器。 如需檔案中參數的詳細說明，請 [!DNL Insight.cfg] 參閱Insight設定 [參數](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。
1. 對要配置連接的每台伺服器重複步驟1和步驟2。
1. 要保存配置設定，請按一下右鍵 **[!UICONTROL Insight.cfg (modified)]** 窗口頂部的，然後按一下 **[!UICONTROL Save as Insight.cfg]**。

資料工作台會嘗試使用您指定的設定連線至伺服器。 如果建立了連接，則綠色節點將顯示在中， [!DNL Servers Manager] 如下所示。 如果「資料工作台」無法連線至伺服器，則會顯示紅色節點。

![](assets/vis_SysStat_RedGreenDots.png)

