---
description: 升級Data Workbench 6.2和6.2.2的伺服器元件。
title: DWB Server升級版6.1至6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# DWB伺服器升級：6.1至6.2{#dwb-server-upgrade-to}

升級Data Workbench 6.2和6.2.2的伺服器元件。

## 6.2的升級問題 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* 「歸因」描述檔是為已實作Adobe SC描述檔以採用Analytics(SC/Insight)資料饋送的使用者所設定。 依預設，行銷和轉換事件會作為在規則型模型中評估的預設互動。 如需 [詳細資訊，請參閱部署歸因設定檔](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html) 。
* 對於升級至Data Workbench 6.2的Adobe SC設定檔使用者，如果您未使用預設設定，請確認檔案中的 [!DNL x-bot_id][!DNL SC Fields.cfg] 值已正確解碼，以及 [!DNL x-bot_id] 欄位已正確列在 [!DNL Decoding Instructions.cfg] 和檔 [!DNL Exclude Hit.cfg] 案中。 只有在從預設配置中修改配置檔案時，才會出現此問題。
* 如果您已刪除Adobe SC設定檔檔案中未使用的欄位，則需要更新以容納用於 [!DNL Dataset > Log Processing > SC Fields.cfg] Attribution設定檔的更新欄位值(請參閱 [部署Attribution設定檔](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html))。

## 6.2.2的升級問題 {#section-8704a9ac358246cd81233dd0982d534f}

* 舊版 **[!UICONTROL Browsers]** 描述 **[!UICONTROL Operating Systems]** 檔中不會更新檔案和查閱 **[!UICONTROL Traffic]**[!DNL Lookups\Traffic\Browsers.txt)]&#x200B;檔案(例如， Instead, configuration of the **[!UICONTROL Traffic]** profile will utilize the DeviceAtlas bundle ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) to provide this configuration information.
* 資料工作台 6.2.1 是可供下載 32 位元客戶端應用程式的最後一版。未來的客戶端應用程式僅供下載 64 位元版本，且一律要求使用 Windows 7 或以上作業系統。自 6.1 版本開始，我們推出 64 位元應用程式，並說明 32 位元應用程式記憶體限制。

>[!NOTE]
>
>32位元版本的資料工作台用戶端應用程式在使用叢集和計分功能執行預測模型時，可能會遇到與記憶體限制相關的潛在問題。

