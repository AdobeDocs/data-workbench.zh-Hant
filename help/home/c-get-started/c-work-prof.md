---
description: Data Workbench將設定檔下載至您的電腦。
title: 設定檔
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
exl-id: a140f549-448c-4e34-8eae-ad154fa01f1f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# 設定檔{#profiles}

{{eol}}

Data Workbench將設定檔下載至您的電腦。

如果您是首次載入設定檔，則必須有與 [!DNL Data Workbench server] 並線上運作，讓Data Workbench可從 [!DNL Data Workbench server].

下載設定檔可能需要幾分鐘的時間。 在資料快取開始填滿前，您不應該開始使用設定檔，但您不必等到資料已滿。 您可以在設定檔載入時查看狀態列，以追蹤資料快取的進度、設定檔同步的進度，以及最近處理資料的日期和時間。

>[!NOTE]
>
>在資料快取開始填入之前，您不會在新增的視覺效果中看見資料。

下次載入設定檔時，只有在您與 [!DNL Data Workbench server] 和正線上上工作。 如果您離線工作，則會從電腦的快取載入設定檔及其資料。 在此情況下，您會檢視設定檔版本，以及上次使用設定檔線上時下載的資料。 如需有關線上或離線工作的詳細資訊，請參閱 [離線和線上工作](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

需要變更設定檔時(使用 [!DNL Profile Manager] 或 [!DNL Server Files Manager])，您應該線上工作，以確保您擁有最新版本的設定檔。 如需 [!DNL Profile Manager] 和 [!DNL Server Files Manager]，請參閱 [管理介面](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

如果您無法存取或載入設定檔，則可能需要確認下列項目：

* 您與 [!DNL Data Workbench server] 配置檔案所在的電腦。
* 您擁有存取設定檔的適當權限。

如需協助，請聯絡您的系統管理員。

## 載入或切換設定檔 {#section-c50499d7d8084d7cadfada52df33f5f4}

1. 啟動Data Workbench。
1. 在側欄中，按一下描述檔名稱，然後按一下 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*，其中 *設定檔名稱* 是您要使用的設定檔。

   ![](assets/sidebar_profile.png)

如果這是您第一次載入選取的設定檔，可能需要幾分鐘的時間才能下載足夠的資料來填入視覺效果。

## 在叢集上存取設定檔 {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbench存取在

ata workbench伺服器叢集僅識別Data Workbench設定檔案( [!DNL Insight.cfg])。 從Data Workbench使用者的觀點來看，設定檔只能在一個Data Workbench伺服器(主Data Workbench伺服器)上存取。 不過，來自分析師的查詢請求可以導向至叢集中的任何Data Workbench伺服器。

有關在Data Workbench伺服器群集上運行的配置檔案的詳細資訊，請參見 *《伺服器產品安裝與管理指南》*.
