---
description: 當您將資料集設定檔設定為在Insight Server叢集上執行時，叢集中的所有電腦都會共用該設定檔的所有資料集組態檔。
title: 設定要在叢集上執行的設定檔
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# 設定要在叢集上執行的設定檔{#configuring-a-profile-to-run-on-a-cluster}

當您將資料集設定檔設定為在Insight Server叢集上執行時，叢集中的所有電腦都會共用該設定檔的所有資料集組態檔。

因此，這些檔案中參數的條目必須適用於群集中的所有[!DNL Insight Servers]。 例如，要讀取的日誌檔案的位置、[!DNL Insight Server]要使用的查找檔案以及[!DNL Insight Server]輸出的資料的位置在群集中的所有電腦上必須相同。

在群集的主[!DNL Insight Server]上執行所有配置任務，該主[!DNL Insight Server]是用於編輯配置檔案的。 主版[!DNL Insight Server]上所做的所有保存的配置檔案更改都會自動同步到群集中處理[!DNL Insight Servers]上的檔案。

若要在[!DNL Insight Server]叢集上執行資料集設定檔，您必須依所列順序執行下列程式：

1. [決定由哪些Insight Server處理事件資料](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [在Profile.cfg中指定處理伺服器](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. （如有必要）[修改設定檔的資料集組態檔](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## 決定哪個Insight Server處理事件資料{#section-59b8e3f2b34f49739d544c8740a62fba}

群集進程事件資料中的所有[!DNL Insight Servers]不是必需的。 您可以在群集中指定一個[!DNL Insight Server]作為檔案伺服器單元，該單元儲存源檔案(VSL和日誌檔案)，並將檔案提供給群集中的所有資料處理單元（處理伺服器）。 此設定提供單一事件資料存放庫的好處，並運用叢集中所有處理伺服器的處理能力。 處理伺服器會將資料檔案分割，並保證不會多次處理相同的檔案。

有關指定[!DNL Insight Server]作為檔案伺服器單元運行的詳細資訊，請參閱&#x200B;*資料集配置指南*&#x200B;中的「日誌處理配置檔案」一章。

如果您決定將來源資料檔案儲存在每個處理伺服器上，而非儲存在單一檔案伺服器單元上，則必須將檔案平分給處理伺服器。 請勿在每個處理伺服器上儲存資料集的所有來源檔案。 如果多個處理伺服器可使用同一檔案的多個副本，則會多次讀取資料（每台電腦一次）並影響資料的準確度。

如需有關確定哪個[!DNL Insight Servers]應處理日誌檔案的幫助，請與Adobe咨詢聯繫。

## 在Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}中指定處理伺服器

在[!DNL profile.cfg]檔案中，指定處理設定檔資料的處理伺服器。

**若要存取profile.cfg檔案**

可使用[!DNL Insight]中的[!DNL Profile Manager]訪問配置檔案配置檔案。

1. 在使用資料集設定檔時，在工作區中按一下滑鼠右鍵並按一下「**[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**」 ，或在「[!DNL Admin]」標籤上開啟「設定檔管理」工作區，以開啟「[!DNL Profile Manager]」。

1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL profile.cfg]旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。

1. 按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 將出現配置檔案配置窗口。

**新增處理伺服器的方式**

1. 在[!DNL profile.cfg]檔案中，按一下&#x200B;**[!UICONTROL Profile]**，然後按一下&#x200B;**[!UICONTROL Processing Servers]**&#x200B;以顯示其內容。

1. 按一下右鍵&#x200B;**[!UICONTROL Processing Servers]**，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**。

1. 在「公用名稱」參數中，鍵入群集中第一個處理伺服器的公用名稱。 例如︰[!DNL server1.mycompany.com]
1. 重複步驟2和3，直到添加群集中所有處理伺服器的通用名稱為止。

   >[!NOTE]
   >
   >如果主[!DNL Insight Server]處理資料，您也必須添加資料。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

1. 在[!DNL profile.cfg]旁的[!DNL User]欄中按一下右鍵複選標籤。 按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*。

## 修改設定檔{#section-99bf9248e4e5483cb518f453b0a2f278}的資料集組態檔

**修改資料集組態檔的方式**

如果您需要變更資料集組態檔（[!DNL Log Processing.cfg]、[!DNL Transformation.cfg]、資料集包含檔案、[!DNL Log Processing Mode.cfg]等），請僅在主版[!DNL Insight Server]進行變更。

1. 訪問要修改的檔案：

   如需存取檔案的指示，請參閱&#x200B;*資料集組態指南*。
1. 進行變更。如需設定檔案中參數的詳細資訊，請參閱&#x200B;*資料集設定指南* 。
1. 儲存檔案。

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 按一下右鍵檔案名旁的[!DNL User]列中的複選標籤。
   1. 按一下&#x200B;**[!UICONTROL Save to]**&#x200B;並選取所需的設定檔。

>[!NOTE]
>
>[!DNL Insight] 存取叢集上執行之資料集設定檔的使用者，只會識別設 [!DNL Insight Server] 定檔 [!DNL Insight] 中的主檔案( [!DNL insight.cfg])。從[!DNL Insight]使用者的角度來看，設定檔只能在一個[!DNL Insight Server]（主[!DNL Insight Server]）上存取；不過，來自分析師的查詢請求可以導向至叢集中的任何[!DNL Insight Servers]。

[!DNL Insight Server]群集允許將[!DNL .vsl]日誌檔案（來自[!DNL Sensor]）集中儲存在名為檔案伺服器單元(FSU)的單個[!DNL Insight Server]電腦上。 有關安裝FSU的資訊，請參閱[Insight Server FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)的安裝程式。 如需設定FSU的相關資訊，請參閱&#x200B;*資料集設定指南*。
