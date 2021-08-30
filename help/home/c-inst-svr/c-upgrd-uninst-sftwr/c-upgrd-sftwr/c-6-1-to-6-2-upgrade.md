---
description: 升級Data Workbench6.2和6.2.2的伺服器元件。
title: DWB伺服器6.1升級至6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 18%

---

# DWB 伺服器升級：6.1 升級至 6.2{#dwb-server-upgrade-to}

升級Data Workbench6.2和6.2.2的伺服器元件。

## 6.2的升級問題 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* 歸因設定檔是為已實作AdobeSC設定檔，以採用Analytics(SC/Insight)資料摘要的使用者所設定。 依預設，行銷和轉換事件會作為規則型模型中評估的預設互動。 如需詳細資訊，請參閱[部署歸因設定檔](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en) 。
* 對於升級到Data Workbench6.2的AdobeSC配置檔案的用戶，如果未使用預設配置，請驗證[!DNL SC Fields.cfg]檔案中的[!DNL x-bot_id]值是否正確解碼，以及[!DNL x-bot_id]欄位是否正確列在[!DNL Decoding Instructions.cfg]和[!DNL Exclude Hit.cfg]檔案中。 只有當您從預設設定修改設定檔案時，才會發生此問題。
* 如果您已刪除AdobeSC設定檔的[!DNL Dataset > Log Processing > SC Fields.cfg]檔案中未使用的欄位，則需要更新以容納用于歸因設定檔的更新欄位值（請參閱[部署歸因設定檔](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)）。

## 6.2.2的升級問題 {#section-8704a9ac358246cd81233dd0982d534f}

* 舊版&#x200B;**[!UICONTROL Traffic]**&#x200B;設定檔中的&#x200B;**[!UICONTROL Browsers]**&#x200B;和&#x200B;**[!UICONTROL Operating Systems]**&#x200B;查閱檔案將不會更新（例如[!DNL Lookups\Traffic\Browsers.txt)]）。 相反，**[!UICONTROL Traffic]**&#x200B;配置檔案將利用DeviceAtlas捆綁包([!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle])提供此配置資訊。
* 資料工作台 6.2.1 是可供下載 32 位元客戶端應用程式的最後一版。未來的客戶端應用程式僅供下載 64 位元版本，且一律要求使用 Windows 7 或以上作業系統。自 6.1 版本開始，我們推出 64 位元應用程式，並說明 32 位元應用程式記憶體限制。

>[!NOTE]
>
>32位版本的Data Workbench客戶端應用程式在使用群集和計分功能運行預測模型時可能遇到與記憶體限制相關的潛在問題。
