---
description: 通訊設定檔Communications.cfg包含Insight Server網路設定和Access Control.cfg檔案的路徑。
solution: Analytics
title: 設定通訊
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---


# 設定通訊{#configuring-communications}

通訊設定檔Communications.cfg包含Insight Server網路設定和Access Control.cfg檔案的路徑。

這些設定可協助您連線至 [!DNL Insight Server]。

**建議頻率：** 僅在需要時

**若要檢視並修改[!DNL Insight]**

1. 在「 [!DNL Insight]>」標籤 [!DNL Admin] 中， [!DNL Dataset and Profile] 按一下縮圖以開 **[!UICONTROL Servers Manager]** 啟「伺服器管理員」工作區。
1. 按一下右鍵要配置的 [!DNL Insight Server] 表徵圖，然後按一下 **[!UICONTROL Server Files]**。
1. 在中，單 [!DNL Server Files Manager]擊以 **[!UICONTROL Components]** 查看其內容。 文 [!DNL Communications.cfg] 件位於此目錄中。
1. 按一下右鍵的伺服器名 *稱列中的複選標籤* ，然 [!DNL Communications.cfg] 後按一下 **[!UICONTROL Make Local]**。 複選標籤會出現在的 [!DNL Temp] 列中 [!DNL Communications.cfg]。
1. 在欄中以滑鼠右鍵按一下新建立的核取標 [!DNL Temp] 記，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Insight]**。
1. 在視窗 [!DNL Communications.cfg] 中，按一 **[!UICONTROL component]** 下以檢視其內容。
1. 視需要變更設定。 如需此檔案中可用參數的詳細資訊，請參閱「通 [訊組態設定」](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1)。

   ![步驟資訊](assets/cfg_communications_examplevalues.png)

1. 執行下列動作，將變更儲存至伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]按一下右鍵列中檔案的複選標籤，然 [!DNL Temp] 後選擇 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

