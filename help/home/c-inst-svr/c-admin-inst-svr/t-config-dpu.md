---
description: DPU設定檔DPU.cfg會指定Insight Server的各種效能參數。
title: 設定 DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# 設定 DPU.cfg{#configuring-dpu-cfg}

DPU設定檔DPU.cfg會指定Insight Server的各種效能參數。

這些參數的設定方式取決於資料集大小和其他許多因素。 如需效能調整的協助，請連絡Adobe諮詢服務。

**建議頻率：** 僅在必要時

**變更DPU [!DNL Insight Server] 效能設定**

1. 在[!DNL Insight]中，在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵要配置的[!DNL Insight Server]表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;以查看其內容。 [!DNL DPU.cfg]檔案位於此目錄中。
1. 按一下右鍵[!DNL DPU.cfg]*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL DPU.cfg]的[!DNL Temp]列中出現複選標籤。
1. 在[!DNL Temp]欄中按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在[!DNL DPU.cfg]視窗中，按一下元件以檢視其內容。
1. 視需要變更效能和路徑設定。 有關此檔案中可用參數的清單，請參閱[DPU效能設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1)。

   >[!NOTE]
   >
   >在更改此檔案中的任何參數之前，請與Adobe聯繫。

   ![](assets/cfg_DPU_egvalues.png)

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，按一下右鍵[!DNL Temp]列中檔案的複選標籤，然後選擇&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。
