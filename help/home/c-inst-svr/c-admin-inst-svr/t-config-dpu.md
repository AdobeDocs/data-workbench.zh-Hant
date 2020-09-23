---
description: DPU設定檔DPU.cfg會指定Insight Server的各種效能參數。
solution: Analytics
title: 設定 DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---


# 設定 DPU.cfg{#configuring-dpu-cfg}

DPU設定檔DPU.cfg會指定Insight Server的各種效能參數。

這些參數的設定方式取決於您的資料集大小和其他許多因素。 如需效能調整的協助，請連絡Adobe諮詢服務。

**建議頻率：** 僅在需要時

**若要變更[!DNL Insight Server]DPU效能設定**

1. 在「 [!DNL Insight]>」標籤 [!DNL Admin] 中， [!DNL Dataset and Profile] 按一下縮圖以開 **[!UICONTROL Servers Manager]** 啟「伺服器管理員」工作區。
1. 按一下右鍵要配置的 [!DNL Insight Server] 表徵圖，然後按一下 **[!UICONTROL Server Files]**。
1. 在中，單 [!DNL Server Files Manager]擊以 **[!UICONTROL Components]** 查看其內容。 文 [!DNL DPU.cfg] 件位於此目錄中。
1. 按一下右鍵的伺服器名 *稱列中的複選標籤* ，然 [!DNL DPU.cfg] 後按一下 **[!UICONTROL Make Local]**。 複選標籤會出現在的 [!DNL Temp] 列中 [!DNL DPU.cfg]。
1. 在欄中以滑鼠右鍵按一下新建立的核取標 [!DNL Temp] 記，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Insight]**。
1. 在窗口 [!DNL DPU.cfg] 中，按一下元件查看其內容。
1. 視需要變更效能和路徑設定。 如需此檔案中可用參數的清單，請參閱 [DPU效能設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1)。

   >[!NOTE]
   >
   >變更此檔案中的任何參數前，請先與Adobe聯絡。

   ![](assets/cfg_DPU_egvalues.png)

1. 執行下列動作，將變更儲存至伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]按一下右鍵列中檔案的複選標籤，然 [!DNL Temp] 後選擇 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

