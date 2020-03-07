---
description: 處理Insight Server與主Insight Server相同，但其「元件」目錄的內容除外。
solution: Insight
title: 安裝和配置Processing Insight伺服器
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安裝和配置Processing Insight伺服器{#installing-and-configuring-the-processing-insight-servers}

處理Insight Server與主Insight Server相同，但其「元件」目錄的內容除外。

處理中的「元件」目 [!DNL Insight Server] 錄包含一組特殊的檔案，這些檔案是專為處理而設 [!DNL Insight Servers]定。 這些檔案是從主伺服器上的「處理伺服器元件」目錄派生的 [!DNL Insight Server]。

安裝處理時， [!DNL Insight Server]請執行下列操作以設定其元件目錄：

1. 刪除處理中的原始「元件」目錄 [!DNL Insight Server]。
1. 將「處理伺服器的元件」目錄更名為「元件」。
1. 修改「 [!DNL Synchronize.cfg] 元件」目錄中的，以指向主目錄 [!DNL Insight Server]。

**若要安裝和設定處理[!DNL Insight Server]**

1. 按照安 [!DNL Insight Server] 裝Insight Server Program Files中 [所述安裝程式檔案](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)。 請務必複製主版上使用的目錄結構 [!DNL Insight Server]。 例如，如果主 [!DNL Insight Server] 版安裝 [!DNL C:\Adobe\Server] 在中，您 [!DNL Insight Server]也必須將它安裝在 [!DNL C:\Adobe\Server] 處理 [!DNL Insight Servers] 中。
1. 安裝Adobe為此特定處理所核發的數位憑證 [!DNL Insight Server]。 如需 [指示，請參閱下載和安裝數位憑證](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) 。
1. 使用Windows檔案總管，在處理中執行下列動作 [!DNL Insight Server]:

   1. Delete the **[!UICONTROL Components]** folder.
   1. 將資料夾 [!DNL Components for Processing Servers] 更名為「元件」。

1. 使用文本編輯器（如記事本），在 [!DNL Synchronize.cfg] 處理中的「元件」目錄中開啟檔案 [!DNL Insight Server]。
1. 將主檔案（主檔案）的IP地址 [!DNL Insight Server] 添加到此檔案的第二行，如以下檔案片段所示。 請勿在此檔案中編輯任何其他內容。

   ```
   component = SynchronizeComponent:
     Cluster Primary Server Address = string: PrimaryIPAddress
     Directories = vector: 7 items
       0 = SynchronizeDir:
         Local Path = string: Profiles\\
         Remote URI = string: /Profiles/
       1 = SynchronizeDir:
         Local Path = string: Lookups\\
         Remote URI = string: /Lookups/
       . . .
   ```

1. 儲存檔案。
1. 如將Insight Server注 [!DNL Insight Server] 冊為Windows服 [務中所述啟動](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。

   您現在已完成叢集的安 [!DNL Insight Server] 裝。 接著，依照下節所述，設定要在叢集上執行的資料集描述檔。

