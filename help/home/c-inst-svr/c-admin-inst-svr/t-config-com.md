---
description: 通訊設定檔Communications.cfg包含Insight Server網路設定和Access Control.cfg檔案的路徑。
title: 設定通訊
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# 設定通訊{#configuring-communications}

通訊設定檔Communications.cfg包含Insight Server網路設定和Access Control.cfg檔案的路徑。

這些設定可協助您連線至[!DNL Insight Server]。

**建議頻率：僅** 在必要時

**若要檢視並修改[!DNL Insight]**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵要配置的[!DNL Insight Server]表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;查看其內容。 [!DNL Communications.cfg]檔案位於此目錄中。
1. 按一下右鍵[!DNL Communications.cfg]*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL Communications.cfg]的[!DNL Temp]欄中會出現複選標籤。
1. 在[!DNL Temp]欄中按一下新建立的核取標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在[!DNL Communications.cfg]窗口中，按一下&#x200B;**[!UICONTROL component]**&#x200B;查看其內容。
1. 視需要變更設定。 有關此檔案中可用參數的資訊，請參閱[通信配置設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1)。

   ![步驟資訊](assets/cfg_communications_examplevalues.png)

1. 執行下列動作，將變更儲存至伺服器：

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，按一下右鍵[!DNL Temp]列中檔案的複選標籤，然後選擇&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]**>*。
