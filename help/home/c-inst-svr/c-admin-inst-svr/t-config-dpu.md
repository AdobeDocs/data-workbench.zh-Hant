---
description: DPU設定檔DPU.cfg會指定Insight Server的各種效能參數。
title: 設定 DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# 設定 DPU.cfg{#configuring-dpu-cfg}

{{eol}}

DPU設定檔DPU.cfg會指定Insight Server的各種效能參數。

這些參數的設定方式取決於資料集大小和其他許多因素。 如需效能調整的協助，請連絡Adobe諮詢服務。

**建議頻率：** 僅在必要時

**若要變更 [!DNL Insight Server] DPU效能設定**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。
1. 以滑鼠右鍵按一下 [!DNL Insight Server] 要配置，請按一下 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Components]** 來檢視其內容。 此 [!DNL DPU.cfg] 檔案位於此目錄中。
1. 以滑鼠右鍵按一下 *伺服器名稱* 欄 [!DNL DPU.cfg] 按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL DPU.cfg].
1. 在 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 在 [!DNL DPU.cfg] ，按一下「元件」查看其內容。
1. 視需要變更效能和路徑設定。 如需此檔案中可用參數的清單，請參閱 [DPU效能設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >在更改此檔案中的任何參數之前，請與Adobe聯繫。

   ![](assets/cfg_DPU_egvalues.png)

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，請在 [!DNL Temp] 欄和選取 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
