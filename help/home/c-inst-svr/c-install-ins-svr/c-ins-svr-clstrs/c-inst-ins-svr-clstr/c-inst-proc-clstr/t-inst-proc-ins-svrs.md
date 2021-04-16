---
description: 處理Insight Server與主Insight Server相同，但其「元件」目錄的內容除外。
title: 安裝和設定處理 Insight Server
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# 安裝和設定處理 Insight Server{#installing-and-configuring-the-processing-insight-servers}

處理Insight Server與主Insight Server相同，但其「元件」目錄的內容除外。

處理[!DNL Insight Server]上的Components目錄包含一組專門配置用於處理[!DNL Insight Servers]的特殊檔案。 這些檔案是從主[!DNL Insight Server]上的「處理伺服器元件」目錄派生的。

當安裝處理[!DNL Insight Server]時，請執行以下操作以設定其元件目錄：

1. 刪除處理[!DNL Insight Server]中的原始「元件」目錄。
1. 將「處理伺服器的元件」目錄更名為「元件」。
1. 修改Components目錄中的[!DNL Synchronize.cfg]以指向主目錄[!DNL Insight Server]。

**若要安裝和設定處理[!DNL Insight Server]**

1. 按照[安裝Insight Server程式檔案](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)中所述安裝[!DNL Insight Server]程式檔案。 請確保複製主[!DNL Insight Server]上使用的目錄結構。 例如，如果[!DNL Insight Server]安裝在主版[!DNL Insight Server]的[!DNL C:\Adobe\Server]中，則您也必須在處理[!DNL Insight Servers]的[!DNL C:\Adobe\Server]中安裝它。
1. 安裝Adobe為此特定處理核發的數位憑證[!DNL Insight Server]。 如需指示，請參閱[下載和安裝數位憑證](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. 使用Windows檔案總管，在處理[!DNL Insight Server]時執行下列動作：

   1. 刪除&#x200B;**[!UICONTROL Components]**&#x200B;資料夾。
   1. 將[!DNL Components for Processing Servers]資料夾重新命名為「元件」。

1. 使用文本編輯器（如記事本），在處理[!DNL Insight Server]的「元件」目錄中開啟[!DNL Synchronize.cfg]檔案。
1. 將主檔案（主檔案）[!DNL Insight Server]的IP地址添加到此檔案的第二行，如以下檔案片段所示。 請勿在此檔案中編輯任何其他內容。

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
1. 按照[將Insight Server註冊為Windows服務](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)中所述啟動[!DNL Insight Server]。

   您現在已完成[!DNL Insight Server]群集的安裝。 接著，依照下節所述，設定要在叢集上執行的資料集描述檔。
