---
description: 當您將資料集設定檔設定為在Insight Server叢集上執行時，叢集中的所有電腦都會共用該設定檔的所有資料集組態檔。
title: 設定要在叢集上執行的設定檔
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# 設定要在叢集上執行的設定檔{#configuring-a-profile-to-run-on-a-cluster}

{{eol}}

當您將資料集設定檔設定為在Insight Server叢集上執行時，叢集中的所有電腦都會共用該設定檔的所有資料集組態檔。

因此，這些檔案中參數的條目必須適用於所有 [!DNL Insight Servers] 在叢集中。 例如，要讀取的日誌檔案的位置，要使用的查閱檔案 [!DNL Insight Server]，以及資料輸出位置(依 [!DNL Insight Server] 在群集中的所有電腦上必須相同。

在群集的主伺服器上執行所有配置任務 [!DNL Insight Server]，即 [!DNL Insight Server] 可用來編輯配置檔案。 在主版上所做的所有已保存的配置檔案更改 [!DNL Insight Server] 會自動同步至處理中的檔案 [!DNL Insight Servers] 在叢集中。

若要在 [!DNL Insight Server] 群集中，您必須按所列順序執行以下進程：

1. [決定由哪些Insight Server處理事件資料](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [在Profile.cfg中指定處理伺服器](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. （如有必要） [修改設定檔的資料集組態檔](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## 決定由哪些Insight Server處理事件資料 {#section-59b8e3f2b34f49739d544c8740a62fba}

並非所有 [!DNL Insight Servers] 在群集進程事件資料中。 您可以指定一個 [!DNL Insight Server] 在群集中作為檔案伺服器單元，該單元儲存源檔案(VSL和日誌檔案)，並將檔案提供給群集中的所有資料處理單元（處理伺服器）。 此設定提供單一事件資料存放庫的好處，並運用叢集中所有處理伺服器的處理能力。 處理伺服器會將資料檔案分割，並保證不會多次處理相同的檔案。

如需有關指定 [!DNL Insight Server] 若要以檔案伺服器單位的形式執行，請參閱 *資料集組態指南*.

如果您決定將來源資料檔案儲存在每個處理伺服器上，而非儲存在單一檔案伺服器單元上，則必須將檔案平分給處理伺服器。 請勿在每個處理伺服器上儲存資料集的所有來源檔案。 如果多個處理伺服器可使用同一檔案的多個副本，則會多次讀取資料（每台電腦一次）並影響資料的準確度。

如需協助，請判斷 [!DNL Insight Servers] 應處理記錄檔，請聯絡Adobe諮詢。

## 在Profile.cfg中指定處理伺服器 {#section-99664e072c21462f91fbafb6d893fcf9}

在 [!DNL profile.cfg] 檔案中，指定處理設定檔資料的處理伺服器。

**若要存取profile.cfg檔案**

您可以使用 [!DNL Profile Manager] in [!DNL Insight].

1. 使用資料集設定檔時，請開啟 [!DNL Profile Manager] 在工作區中按一下滑鼠右鍵，然後按一下 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**，或在 [!DNL Admin] 標籤。

1. 在 [!DNL Profile Manager]，按一下右鍵旁的複選標籤 [!DNL profile.cfg] 按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。

1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. 將出現配置檔案配置窗口。

**新增處理伺服器的方式**

1. 在 [!DNL profile.cfg] 檔案，按一下 **[!UICONTROL Profile]**，然後按一下 **[!UICONTROL Processing Servers]** 來顯示其內容。

1. 按一下右鍵 **[!UICONTROL Processing Servers]** 按一下 **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. 在「公用名稱」參數中，鍵入群集中第一個處理伺服器的公用名稱。 例如︰[!DNL server1.mycompany.com]
1. 重複步驟2和3，直到添加群集中所有處理伺服器的通用名稱為止。

   >[!NOTE]
   >
   >如果主 [!DNL Insight Server] 處理資料，您也必須新增資料。

1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

1. 以滑鼠右鍵按一下 [!DNL User] 欄旁邊 [!DNL profile.cfg]. 按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## 修改設定檔的資料集組態檔 {#section-99bf9248e4e5483cb518f453b0a2f278}

**修改資料集組態檔的方式**

如果您需要變更資料集組態檔( [!DNL Log Processing.cfg], [!DNL Transformation.cfg]，資料集包含檔案， [!DNL Log Processing Mode.cfg]等)，僅對主版執行 [!DNL Insight Server].

1. 訪問要修改的檔案：

   如需存取檔案的指示，請參閱 *資料集組態指南*.
1. 進行變更。請參閱 *資料集組態指南* 如需設定檔案中參數的詳細資訊。
1. 儲存檔案。

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 以滑鼠右鍵按一下 [!DNL User] 欄。
   1. 按一下 **[!UICONTROL Save to]** ，然後選取所需的設定檔。

>[!NOTE]
>
>[!DNL Insight] 存取叢集上執行之資料集設定檔的使用者僅識別主資料 [!DNL Insight Server] 在 [!DNL Insight] 配置檔案( [!DNL insight.cfg])。 從 [!DNL Insight] 使用者，只能透過一個 [!DNL Insight Server] (主 [!DNL Insight Server]);不過，來自分析師的查詢請求可導向至 [!DNL Insight Servers] 在叢集中。

安 [!DNL Insight Server] 群集允許集中儲存 [!DNL .vsl] 日誌檔案(從 [!DNL Sensor]) [!DNL Insight Server] 名為檔案伺服器單元(FSU)的電腦。 如需安裝FSU的詳細資訊，請參閱 [Insight Server FSU的安裝程式](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). 如需設定FSU的詳細資訊，請參閱 *資料集組態指南*.
