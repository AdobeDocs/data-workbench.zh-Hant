---
description: 處理Insight Server與主Insight Server相同，但其元件目錄的內容除外。
title: 安裝和設定處理 Insight Server
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# 安裝和設定處理 Insight Server{#installing-and-configuring-the-processing-insight-servers}

{{eol}}

處理Insight Server與主Insight Server相同，但其元件目錄的內容除外。

處理程式上的元件目錄 [!DNL Insight Server] 包含一組專門配置用於處理的特殊檔案 [!DNL Insight Servers]. 這些檔案是從主伺服器上的「處理伺服器元件」目錄派生的 [!DNL Insight Server].

安裝處理程式時 [!DNL Insight Server]，請執行以下操作來設定其元件目錄：

1. 在處理時刪除原始的「元件」目錄 [!DNL Insight Server].
1. 將「處理伺服器的元件」目錄重新命名為「元件」。
1. 修改 [!DNL Synchronize.cfg] （在「元件」目錄中）以指向主版 [!DNL Insight Server].

**安裝及設定處理[!DNL Insight Server]**

1. 安裝 [!DNL Insight Server] 程式檔案，如 [安裝Insight Server程式檔案](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). 請務必複製主版上使用的目錄結構 [!DNL Insight Server]. 例如，若 [!DNL Insight Server] 安裝於 [!DNL C:\Adobe\Server] 在主人 [!DNL Insight Server]，您必須在 [!DNL C:\Adobe\Server] 處理時 [!DNL Insight Servers] 還有。
1. 安裝Adobe為此特定處理簽發的數位憑證 [!DNL Insight Server]. 請參閱 [下載和安裝數位憑證](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) 的說明。
1. 使用Windows資源管理器，在處理過程中執行以下操作 [!DNL Insight Server]:

   1. 刪除 **[!UICONTROL Components]** 檔案夾。
   1. 重新命名 [!DNL Components for Processing Servers] 檔案夾中。

1. 使用文本編輯器（如記事本），開啟 [!DNL Synchronize.cfg] 檔案（位於「元件」目錄中） [!DNL Insight Server].
1. 添加主（主）的IP地址 [!DNL Insight Server] 到此檔案的第二行，如下列檔案片段所示。 請勿在此檔案中編輯任何其他內容。

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
1. 啟動 [!DNL Insight Server] 如 [將Insight Server註冊為Windows服務](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   您現在已完成 [!DNL Insight Server] 群集。 接著，依照下節所述，設定要在叢集上執行的資料集設定檔。
