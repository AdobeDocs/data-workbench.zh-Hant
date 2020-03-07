---
description: 當您將資料集描述檔設定為在Insight Server叢集上執行時，叢集中的所有電腦都會共用該描述檔的所有資料集設定檔案。
solution: Insight
title: 配置要在群集上運行的配置檔案
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置要在群集上運行的配置檔案{#configuring-a-profile-to-run-on-a-cluster}

當您將資料集描述檔設定為在Insight Server叢集上執行時，叢集中的所有電腦都會共用該描述檔的所有資料集設定檔案。

因此，這些檔案中參數的條目必須適用於群集中 [!DNL Insight Servers] 的所有條目。 例如，要讀取的日誌檔案位置、要由使用的查找檔案以及由輸出的資料在群集中 [!DNL Insight Server][!DNL Insight Server] 的所有電腦上的位置必須相同。

您可在叢集的主版上執行所有設定工 [!DNL Insight Server]作，而此為您 [!DNL Insight Server] 用來編輯設定檔案的工具。 在主系統上所做的所有保存的配置檔案更 [!DNL Insight Server] 改都將自動同步到集群中處理過程中 [!DNL Insight Servers] 的檔案。

要在群集上運行資料集配 [!DNL Insight Server] 置檔案，必須按所列順序執行以下進程：

1. [確定哪個Insight Server處理事件資料](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [在Profile.cfg中指定處理伺服器](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. （如有必要） [修改配置檔案的資料集配置檔案](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## 確定哪個Insight Server處理事件資料 {#section-59b8e3f2b34f49739d544c8740a62fba}

群集中的所有事件數 [!DNL Insight Servers] 據不是必需的。 您可以將群集中 [!DNL Insight Server] 的一個檔案伺服器單元指定為檔案伺服器單元，該檔案伺服器單元儲存源檔案（VSL和日誌檔案），並將檔案提供給群集中的所有資料處理單元（處理伺服器）。 此設定提供了單個事件資料儲存庫的優點，並利用了群集中所有處理伺服器的處理能力。 處理伺服器將資料檔案分割，並保證同一檔案不會多次處理一次。

有關指定運行為檔案服 [!DNL Insight Server] 務器單元的詳細資訊，請參閱資料集配置指南的「日誌處理配置文 *件」一章*。

如果您決定將來源資料檔案儲存在每個處理伺服器上，而非儲存在單一檔案伺服器單元上，則必須在處理伺服器之間平均分割檔案。 請勿將資料集的所有來源檔案儲存在每個處理伺服器上。 如果同一檔案的多個副本可用於多個處理伺服器，則會多次讀取資料（每台電腦一次）並使資料傾斜。

如需決定應處理記 [!DNL Insight Servers] 錄檔的說明，請聯絡Adobe Consulting。

## 在Profile.cfg中指定處理伺服器 {#section-99664e072c21462f91fbafb6d893fcf9}

在檔案 [!DNL profile.cfg] 中，指定處理描述檔資料的處理伺服器。

**若要存取profile.cfg檔案**

使用中訪問配置檔案 [!DNL Profile Manager] 配置文 [!DNL Insight]件。

1. 在資料集描述檔中工作時，在工 [!DNL Profile Manager] 作區中按一下滑鼠右鍵，然後按一下 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**，或在標籤上開啟描述檔管理工作區，以開啟 [!DNL Admin] 該工作區。

1. 在中， [!DNL Profile Manager]按一下右鍵旁邊的複選標籤並 [!DNL profile.cfg] 按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。

1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Insight]**。 將出現配置檔案配置窗口。

**若要新增處理伺服器**

1. 在檔案 [!DNL profile.cfg] 中，按一下 **[!UICONTROL Profile]**，然後按 **[!UICONTROL Processing Servers]** 一下以顯示其內容。

1. 以滑鼠右鍵按 **[!UICONTROL Processing Servers]** 一下，然後按 **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**。

1. 在「公用名稱」參數中，鍵入群集中第一個處理伺服器的公用名稱。 例如︰[!DNL server1.mycompany.com]
1. 重複步驟2和3，直到添加集群中所有處理伺服器的公用名稱。

   >[!NOTE]
   >
   >如果主程式 [!DNL Insight Server] 處理資料，您也必須添加資料。

1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。

1. 按一下右鍵旁邊列中 [!DNL User] 的複選標籤 [!DNL profile.cfg]。 按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## 修改配置檔案的資料集配置檔案 {#section-99bf9248e4e5483cb518f453b0a2f278}

**修改資料集配置檔案**

如果您需要變更資料集設定檔案( [!DNL Log Processing.cfg]、 [!DNL Transformation.cfg]、資料集包含檔案 [!DNL Log Processing Mode.cfg]等)，請僅在主版上進行變更 [!DNL Insight Server]。

1. 訪問要修改的檔案：

   如需存取檔案的指示，請參閱資料集 *設定指南*。
1. 進行變更。有關配 *置檔案中參數的詳細資訊* ，請參閱資料集配置指南。
1. 儲存檔案。

   1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。

   1. 按一下右鍵檔案名旁 [!DNL User] 列中的複選標籤。
   1. 按一 **[!UICONTROL Save to]** 下並選取所要的描述檔。

>[!NOTE]
>
>[!DNL Insight] 存取在叢集上執行之資料集描述檔的使用者，只會識別 [!DNL Insight Server] 設定檔 [!DNL Insight] 案( [!DNL insight.cfg])中的主檔案。 從使用者的角 [!DNL Insight] 度來看，描述檔只能在一個(主版 [!DNL Insight Server][!DNL Insight Server])上存取；但是，分析師的查詢請求可以定向到群集中 [!DNL Insight Servers] 的任一個。

群 [!DNL Insight Server] 集允許將日誌檔案（來自）集中 [!DNL .vsl] 儲存在名為「檔案伺服器單 [!DNL Sensor][!DNL Insight Server] 元」(FSU)的單台電腦上。 如需有關安裝FSU的詳細資訊，請參 [閱Insight Server FSU的安裝程式](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)。 如需設定FSU的詳細資訊，請參閱資料集 *設定指南*。
