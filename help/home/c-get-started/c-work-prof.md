---
description: 資料工作台會將描述檔下載至您的電腦。
title: 設定檔
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Profiles{#profiles}

資料工作台會將描述檔下載至您的電腦。

如果您是第一次載入描述檔，則必須有與的網路連線，而且必須連線 [!DNL Data Workbench server] ，才能讓資料工作台從下載必要的檔案 [!DNL Data Workbench server]。

下載描述檔可能需要幾分鐘的時間。 在「資料快取」開始填滿之前，您不應開始使用描述檔，但您不必等到描述檔已滿。 您可以在描述檔載入時查看狀態列，以追蹤資料快取的進度、描述檔同步的進度，以及最近處理資料的日期和時間。

>[!NOTE]
>
>在資料快取開始填滿之前，您不會在您新增的視覺化中看到資料。

下次載入描述檔時，只有在您與之有網路連線且正線上上運作時，才會下載描述檔的更新 [!DNL Data Workbench server] 及其資料。 如果您離線工作，描述檔及其資料會從您電腦的快取載入。 在這種情況下，您正在查看上次聯機處理配置檔案時下載的配置檔案和資料的版本。 如需有關線上與離線工作的詳細資訊，請參 [閱線下與線上工作](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54)。

當您需要變更個人檔案(使 [!DNL Profile Manager] 用或 [!DNL Server Files Manager])時，您應線上工作，以確保您擁有最新版的個人檔案。 有關和的詳細信 [!DNL Profile Manager] 息，請 [!DNL Server Files Manager]參 [閱管理介面](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74)。

如果您無法存取或載入描述檔，可能需要確認下列事項：

* 您與配置檔案所在 [!DNL Data Workbench server] 的電腦有網路連接。
* 您擁有存取描述檔的適當權限。

如需協助，請連絡您的系統管理員。

## 載入或切換描述檔 {#section-c50499d7d8084d7cadfada52df33f5f4}

1. 啟動資料工作台。
1. 在側欄中，按一下配置檔案名稱，然後按一下 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*，其中 *配置檔案名稱* ，您要使用配置檔案。

   ![](assets/sidebar_profile.png)

如果這是您第一次載入選取的描述檔，可能需要幾分鐘的時間下載足夠的資料以填入視覺化。

## 訪問群集上的配置檔案 {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

存取在

資料工作台伺服器叢集僅識別「資料工作台」設定檔( [!DNL Insight.cfg])中的主資料工作台伺服器。 從資料工作台使用者的角度來看，描述檔只能在一個資料工作台伺服器（主資料工作台伺服器）上存取。 不過，分析師的查詢請求可以導向至叢集中的任何資料工作台伺服器。

如需在資料工作台伺服器叢集上執行之描述檔的詳細資訊，請參 *閱伺服器產品安裝與管理指南*。
