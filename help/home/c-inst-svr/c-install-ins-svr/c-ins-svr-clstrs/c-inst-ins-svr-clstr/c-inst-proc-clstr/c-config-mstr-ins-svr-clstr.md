---
description: 有關在主Insight Server上設定叢集、更新叢集存取控制檔案等的資訊。
title: 為叢集設定主 Insight Server
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# 為叢集設定主 Insight Server{#configuring-the-master-insight-server-for-clustering}

{{eol}}

有關在主Insight Server上設定叢集、更新叢集存取控制檔案等的資訊。

要配置群集，請在主伺服器上執行以下步驟 [!DNL Insight Server]:

* 新增處理 [!DNL Insight Servers’] 地址檔案的常見名稱和地址。
* 新增所有 [!DNL Insight Servers] 到 [!DNL Access Control.cfg] 檔案。

* 更新 [!DNL Synchronize.cfg] 檔案（位於「處理伺服器的元件」目錄中），以指向主伺服器 [!DNL Insight Server].

* 如有必要，請修改 [!DNL Disk Files.cfg] 檔案（位於「處理伺服器的元件」目錄中），以指定 [!DNL temp.db] 檔案 [!DNL Insight Servers].

若要完成這些步驟，您必須知道通用名稱（如個人的數位憑證上所指定） [!DNL Insight Server])和每個 [!DNL Insight Server] 在叢集中。 如果您尚未獲得此資訊，請在繼續之前獲取此資訊。

>[!NOTE]
>
>本節所述的程式要求 [!DNL Insight]. 如果您尚未安裝 [!DNL Insight]，請遵循 **[!DNL Insight]使用手冊** 開始之前。

## 將處理分析伺服器新增至位址檔案 {#section-2fe5298180164e8dbaa59ea6b6ff682d}

請依照下列程式新增處理程式 [!DNL Insight Servers’] 主檔案上的地址檔案的常見名稱和IP地址 [!DNL Insight Server]. (儘管地址檔案在主檔案上進行維護和管理 [!DNL Insight Server]，則會供所有使用者使用 [!DNL Insight Servers] )。

>[!NOTE]
>
>以下假設已為主檔案配置了地址檔案 [!DNL Insight Server]. 如果尚未添加主版 [!DNL Insight Server’s] IP位址至位址檔案，請完成 [定義伺服器的網路位置](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) 開始之前。

**新增處理程式的方式 [!DNL Insight Servers] 地址檔案**

1. 開始 [!DNL Insight] 並載入「設定」設定檔（如果尚未開啟），方法是以滑鼠右鍵按一下標題列，然後按一下 **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。

1. 按一下右鍵主版的表徵圖 **[!UICONTROL Insight Server]** 按一下 **[!UICONTROL Server Files]**.

1. 在 [!DNL Server Files Manager]，開啟「地址」目錄，然後執行以下操作以開啟 [!DNL Insight Server’s] 地址檔案：

   1. 以滑鼠右鍵按一下 *伺服器名稱* 欄，按一下 **[!UICONTROL Make Local]**.

   1. 以滑鼠右鍵按一下 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. 展開 [!DNL Locations] 結構，然後展開NetworkLocation 0、Addresses和AddressDefinition。
1. 執行以下操作，為每個處理將AddressDefinition添加到NetworkLocation 0 [!DNL Insight Server] 在群集中：

   1. 按一下右鍵 **[!UICONTROL AddressDefinition]** 按一下 **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. 在「名稱」參數中，指定處理 [!DNL Insight Server’s] 常見名稱。
   1. 在「位址」參數中，指定處理 [!DNL Insight Server’s] IP位址。

      您可以在「地址」欄位中使用星號作為通配符，例如10.10.116。&#42;，以簡化叢集。 請參閱 [了解存取層級](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      下列範例定義包含兩個 [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. 如果伺服器已連接到多個網路，請重複步驟6以添加處理 [!DNL Insight Servers] 到這些網路的NetworkLocations。

   下列範例顯示四個叢集 [!DNL Insight Servers] 連接到兩個網路（「企業內聯網」和「網際網路」）。

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，請在 [!DNL Temp] 欄和選取 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## 更新群集的訪問控制檔案 {#section-fce1367d92a445168c35e9ca506e7d6b}

使用 [!DNL Insight Servers] 在群集中，每個 [!DNL Insight Server] 群集(包括主 [!DNL Insight Server])必須屬於群集伺服器存取控制組。 群集伺服器組標識允許參與群集的伺服器（按IP地址）。 雖然此檔案是在主檔案上維護和管理的 [!DNL Insight Server]，所有 [!DNL Insight Servers] 在叢集中。

**要編輯訪問控制檔案**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。

1. 按一下右鍵主版的表徵圖 [!DNL Insight Server] 按一下 **[!UICONTROL Server Files]**.

1. 在 [!DNL Server Files Manager]，開啟「訪問控制」目錄。
1. 執行下列操作以開啟 [!DNL Access Control.cfg] 檔案：

   1. 以滑鼠右鍵按一下 *伺服器名稱* 欄，按一下 **[!UICONTROL Make Local]**.

   1. 以滑鼠右鍵按一下 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. 展開「訪問控制組」結構，然後展開「訪問組」（群集伺服器）。
1. 針對每個 [!DNL Insight Server] 群集(包括主 [!DNL Insight Server])，請執行下列動作：

   1. 按一下右鍵 **[!UICONTROL Members]** 按一下 **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. 指定 [!DNL Insight Server’s] IP位址（其數值IP位址，而非名稱）。 若 [!DNL Insight Servers] 連接到多個網路，此AccessGroup應僅包含內部地址 [!DNL Insight Servers] 用於群集內的伺服器間通信。

      下面顯示了四個群集的AccessGroup（群集伺服器） [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，請在 [!DNL Temp] 欄，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## 配置同步檔案 {#section-d23e751771c84da6bab6a34a8db867bc}

您可以依照下列程式來設定 [!DNL Synchronize.cfg] 檔案。 此檔案的中央副本在主版上維護 [!DNL Insight Server]. 處理 [!DNL Insight Servers] 在群集中，啟動與主機的通信 [!DNL Insight Server] 以擷取此檔案的更新副本。

此 [!DNL Synchronize.cfg] 檔案指定主檔案的位置 [!DNL Insight Server]. 它也會識別每個處理程式的管理檔案集 [!DNL Insight Servers] 叢集中會從主伺服器擷取 [!DNL Insight Server]. 處理 [!DNL Insight Servers] 從主版自動下載這些檔案 [!DNL Insight Server] 開始時。 它們還從主版中動態檢索這些檔案的更新副本 [!DNL Insight Server] 檔案變更時。

>[!NOTE]
>
>雖然您已設定 [!DNL Synchronize.cfg] 檔案 [!DNL Insight Server]，主 [!DNL Insight Server] 本身不會使用此檔案。 在主版上更新此檔案 [!DNL Insight Server] 以便在處理時正確設定 [!DNL Insight Servers] 擷取檔案。

**更新主版上的Synchronize.cfg檔案[!DNL Insight Server]**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。

1. 按一下右鍵主版的表徵圖 [!DNL Insight Server] 按一下 **[!UICONTROL Server Files]**.

1. 在 [!DNL Server Files Manager]，開啟 **[!UICONTROL Components]** （處理伺服器目錄）。

1. 執行下列操作以開啟 [!DNL Synchronize.cfg]:

   1. 以滑鼠右鍵按一下 *伺服器名稱* 欄，按一下 **[!UICONTROL Make Local]**.

   1. 以滑鼠右鍵按一下 [!DNL Temp] 勾選標籤並按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. 展開元件結構。
1. 在群集主伺服器地址參數中，指定主伺服器（主伺服器）的IP地址 **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   要建立日誌，記錄每次主版之間發生同步時的記錄 [!DNL Insight Server] 和處理 [!DNL Insight Servers]，請確保「啟用同步日誌」參數設定為「true」。

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，請在 [!DNL Temp] 欄，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## 設定資料集 (temp.db) 的位置 {#section-5ec257a4b4c64fb58baec1f12119a822}

如果您想要處理，請執行下列程式 [!DNL Insight Servers] 維護 [!DNL temp.db] （資料集），位於與預設位置不同的目錄或驅動器中，或您想要 [!DNL temp.db] 跨多個驅動器。

>[!NOTE]
>
>因為處理 [!DNL Insight Servers] 所有人都有相同的 [!DNL Disk Files.cfg]，所有檔案都必須支援您在此檔案中指定的檔案位置。 例如，若您指派 [!DNL temp.db] 到E:每次處理 [!DNL Insight Server] 在叢集中必須有E:開車。

**配置temp.db的位置**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。

1. 按一下右鍵主版的表徵圖 [!DNL Insight Server] 按一下 **[!UICONTROL Server Files]**.

1. 在 [!DNL Server Files Manager]，開啟 **[!UICONTROL Components for Processing Servers]** 目錄。

1. 執行下列操作以開啟 [!DNL Disk Files.cfg]:

   1. 以滑鼠右鍵按一下 *伺服器名稱* 欄，按一下 **[!UICONTROL Make Local]**.

   1. 以滑鼠右鍵按一下 [!DNL Temp]欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. 展開DiskSpaceManagerComponent結構，然後展開「磁碟檔案」清單。
1. 編輯條目0以更改 [!DNL temp.db] 檔案。
1. 如果您想要分發 [!DNL temp.db] 在多個驅動器上，使用以下步驟為每個附加驅動器建立一個附加條目。

   1. 按一下右鍵 **[!UICONTROL Disk Files]** 按一下 **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. 在新條目中，指定您要的位置 [!DNL temp.db] 已寫入。
   下列顯示 [!DNL temp.db] 寫在四個驅動器上。

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，請在 [!DNL Temp] 欄，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
