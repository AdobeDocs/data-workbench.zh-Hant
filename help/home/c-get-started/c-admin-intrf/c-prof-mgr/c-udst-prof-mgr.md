---
description: 實作中包含的檔案夾和檔案名稱會顯示在「描述檔管理員」的左側。
solution: Analytics
title: 設定檔管理員
topic: Data workbench
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定檔管理員{#profile-manager}

實作中包含的檔案夾和檔案名稱會顯示在「描述檔管理員」的左側。

組成您應用程式的描述檔會顯示為中的個別欄 [!DNL Profile Manager]。 這些描述檔包括多個繼承的描述檔和單一工作描述檔。

>[!NOTE]
>
>您的工作設定檔（資料集設定檔或角色特定設定檔）是您開啟「資料工作台」時載入的設定檔。

複選標籤（及其顏色）表示每個檔案所在之資料工作台伺服器與資料工作台電腦上的描述檔資料夾、檔案是否存在多份復本，以及這些復本是否具有相同的修改日期與時間。 這些檔案會在描述檔下載期間在資料工作台伺服器與資料工作台電腦之間同步。

以下是HBX實 [!DNL Profile Manager] 作的範例：

![](assets/client-prof.png)

從功 [!DNL Profile Manager] 能表，您可以開啟任何其他管理員(例如 [!DNL Dimensions Manager] 或 [!DNL Reports Manager])，這些管理員只顯示特定部分 [!DNL Profile Manager]。 您也可以建立新的描述檔管理員。 請參閱 [建立新的描述檔管理員](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3)。

特定列中檔案名旁的複選標籤表示該名稱的檔案駐留在該列（配置檔案）中命名的資料夾中。 當您移至中的右側時 [!DNL Profile Manager]，檔案優先於左側的檔案，即每個繼承的描述檔會在左側的描述檔上建立 [!DNL Profile Manager]。 例如，如果配置檔案（列）和配置檔案（列）中有相同名稱且位於相同位置的檔案，則 [!DNL Base] 會使用配置檔案中的檔案，而不是配置檔案中的文 [!DNL User][!DNL User][!DNL Base] 件。

## 搜尋描述檔 {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

在「資料工作台5.5」中，已新增搜尋欄位，以在中尋找必要的描述檔 [!DNL Profile Manager]。

![](assets/client-prof2.png)

下列類型的欄會出現在 [!DNL Profile Manager]:

* 繼承 *的配置檔案名稱* 列包含駐留在每個配置檔案資料夾中的檔案的複選標籤。 繼承的個人檔案包括Adobe提供的內部個人檔案，以及您建立和維護的任何公司特定或角色特定個人檔案。 在上述範例中，內部設定檔包括「基本」、「流量」、「值」、「行銷」等。 內部設 [!DNL Base] 定檔包含執行Adobe應用程式所需的基本建置區塊和設定資訊，並隨附於每個實作。 其他內部設定檔包含與特定資訊類型（例如網路流量或行銷）相關的元素（工作區、量度、衍生維度等）。 Adobe僅提供適合您所分析資料類型和您產業的資料設定檔。

   >[!NOTE]
   >
   >依預設，內部設定檔（由Adobe提供的設定檔）無法變更。 所有自訂都必須發生在您的資料集、角色特定的描述檔或您建立的其他描述檔中。 如果您要構建新應用程式並需要更改內部配置檔案，則必須更改檔案中的「修改內部配置檔案」 [!DNL Insight.cfg] 參數。 如需詳 [細資訊，請參閱](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) Insight設定參數。 在這麼做之前，請先與Adobe諮詢服務聯絡。

* 工作 *描述檔名稱* （永遠是倒數第一欄）欄包含目前工作描述檔資料夾中檔案的核取符號。 在上述範例中，工作設定檔為Dataset。 您的工作設定檔是資料集設定檔或角色特定設定檔。 此資料夾中的檔案優先於任何繼承配置檔案資料夾中名稱相同的檔案。
* 該 [!DNL User] 列始終是最後一列，包含User\*profile name*資料夾中作為本地檔案的檔案和資料夾的複選標籤。 「用戶」資料夾的目錄結構與工作配置檔案的目錄結構相似，每個「用戶」\*配置檔案名稱*資料夾都包含該特定配置檔案的工作區、度量、維度和配置檔案的本地副本。 這些本地副本優先於任何繼承或工作配置檔案資料夾中具有相同名稱的任何檔案。 列中的文 [!DNL User] 件建立並僅保存到User\*profile name*資料夾，或者它們位於內部或工作配置檔案以及User\*profile name*資料夾中。 每個資料夾中的檔案可能不相同，也可能不相同，而且修改的日期和時間可能不相同。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 為避免僅在本機更改資料集，資料工作台伺服器會忽略檔案的本地副本以及User\*profile name*資料夾中的Dataset或Export資料夾中的任何檔案。 [!DNL profile.cfg] 忽略的檔案會在欄中以紅色背景 [!DNL User] 識別，而在內容選單中會顯示「在使用者目錄中忽略」警告。 若要在這些檔案的本機副本中實施變更，您必須將這些變更儲存至您的工作設定檔，以便與資料工作台伺服器同步。 有關將檔案保存到工作配置檔案的步驟，請參 [閱將檔案發佈到工作配置檔案](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。
      >    
      >    
   * 連字型大小(-)（而非欄中的勾號）可識別空（零位元組）檔案。 資料工作台將零位元組檔案視為不存在，讓您使用這些檔案將設定檔中包含的檔案隱藏在左側。 請參 [閱使用空（零位元組）檔案隱藏檔案](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491)。


## 確定檔案版本 {#section-225d732246b94cbe87acdfa9c881d6af}

如上節所述，中的複選標籤會以色 [!DNL Profile Manager] 碼標示，以便您輕鬆識別檔案的所在位置，以及是否在不同時間修改了檔案的多個副本。

如果檔案或折疊的目錄與其左側的檔案或目錄完全相同，則其顏色複選標籤與該列（配置檔案）中的檔案或目錄相同。 如果它與其左側的任何檔案或目錄不同，或者檔案或目錄僅存在於列中，則復 [!DNL User] 選標籤為白色。

![](assets/vis_ProfMgr_LocalFiles.png)

上 [!DNL Profile Manager] 述範例中的說明如下：

* 檔案的白勾號只會 [!DNL A New Metric.metric][!DNL User] 出現在欄中，這表示您只有該檔案的本機副本——該檔案尚未發佈（或上傳）至資料工作台伺服器，以供其他資料工作台使用者存取。

* 檔案名稱的 [!DNL Average Score.metric] 勾號會顯示在影片和欄 [!DNL User] 中。 列中的複選標 [!DNL User] 記與「影片」列中的複選標籤顏色相同，這表示檔案的本地副本與「影片」資料夾中的檔案具有相同的「已修改」日期和時間。

* 檔案名稱的 [!DNL Average Score Error.metric] 勾號會顯示在影片和欄 [!DNL User] 中。 該列中的複選標 [!DNL User] 記為白色，表示檔案的本地副本具有與「影片」資料夾中的檔案不同的「已修改」日期或時間。

