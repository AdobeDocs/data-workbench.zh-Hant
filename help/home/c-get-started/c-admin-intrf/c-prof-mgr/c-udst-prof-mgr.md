---
description: 實作中包含的檔案夾和檔案名稱會顯示在「描述檔管理員」的左側。
title: 設定檔管理員
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# 設定檔管理員{#profile-manager}

實作中包含的檔案夾和檔案名稱會顯示在「描述檔管理員」的左側。

組成您應用程式的描述檔會顯示為[!DNL Profile Manager]中的個別欄。 這些描述檔包括多個繼承的描述檔和單一工作描述檔。

>[!NOTE]
>
>您的工作設定檔（資料集設定檔或角色特定設定檔）是您開啟Data Workbench時載入的設定檔。

複選標籤（及其顏色）表示每個檔案所在的Data Workbench伺服器和Data Workbench電腦上的配置檔案資料夾、檔案是否存在多個副本，以及這些副本是否具有相同的修改日期和時間。 這些檔案將在Data Workbench伺服器和Data Workbench電腦之間同步進行配置檔案下載。

以下是實作的範例[!DNL Profile Manager]HBX:

![](assets/client-prof.png)

從[!DNL Profile Manager]菜單，可以開啟任何其它管理器（例如[!DNL Dimensions Manager]或[!DNL Reports Manager]），這些管理器僅顯示[!DNL Profile Manager]的特定部分。 您也可以建立新的描述檔管理員。 請參閱[建立新配置式管理器](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3)。

特定列中檔案名旁的複選標籤表示該名稱的檔案駐留在該列（配置檔案）中命名的資料夾中。 當您在[!DNL Profile Manager]中移到右側時，檔案優先於左側的檔案，即每個繼承的描述檔會在[!DNL Profile Manager]左側的描述檔上建立。 例如，如果您在[!DNL Base]描述檔(column)和[!DNL User]描述檔(column)中有相同名稱且位於相同位置的檔案，則會使用[!DNL User]描述檔中的檔案，而非[!DNL Base]描述檔中的檔案。

## 搜索配置檔案{#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

在Data Workbench5.5中，已新增搜尋欄位，以在[!DNL Profile Manager]中尋找必要的描述檔。

![](assets/client-prof2.png)

[!DNL Profile Manager]中顯示以下類型的列：

* *繼承的配置檔案名稱*&#x200B;列包含駐留在每個配置檔案資料夾中的檔案的複選標籤。 繼承的個人檔案包括由Adobe提供的內部個人檔案，以及您建立和維護的任何公司特定或角色特定個人檔案。 在上述範例中，內部設定檔包括「基本」、「流量」、「值」、「行銷」等。 內部[!DNL Base]描述檔包含執行Adobe應用程式所需的基本建置區塊和設定資訊，隨附於每個實作。 其他內部設定檔包含與特定資訊類型（例如網路流量或行銷）相關的元素（工作區、量度、衍生維度等）。 Adobe僅提供適合您所分析資料類型和您產業的資料設定檔。

   >[!NOTE]
   >
   >依預設，內部描述檔(由Adobe提供的描述檔)無法變更。 所有自訂都必須發生在您的資料集、角色特定的描述檔或您建立的其他描述檔中。 如果要構建新應用程式並需要更改內部配置檔案，則必須更改[!DNL Insight.cfg]檔案中的「修改內部配置檔案」參數。 如需詳細資訊，請參閱[Insight設定參數](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。 在這麼做之前，請聯絡Adobe諮詢服務。

* *工作描述檔名稱*&#x200B;欄永遠是倒數第一欄，包含目前工作描述檔資料夾中檔案的核取符號。 在上述範例中，工作設定檔為Dataset。 您的工作設定檔是資料集設定檔或角色特定設定檔。 此資料夾中的檔案優先於任何繼承配置檔案資料夾中名稱相同的檔案。
* [!DNL User]欄永遠是最後一欄，包含User\*profile name*資料夾中作為本機檔案的檔案和檔案夾的勾號。 「用戶」資料夾的目錄結構與工作配置檔案的目錄結構相似，每個「用戶」\*配置檔案名稱*資料夾都包含該特定配置檔案的工作區、度量、維度和配置檔案的本地副本。 這些本地副本優先於任何繼承或工作配置檔案資料夾中具有相同名稱的任何檔案。 [!DNL User]欄中的檔案已建立並儲存至僅User\*profile name*檔案夾，或者檔案位於內部或運作中的描述檔，以及User\*profile name*檔案夾。 每個資料夾中的檔案可能不相同，也可能不相同，而且修改的日期和時間可能不相同。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 為避免僅在本地更改資料集，Data Workbench伺服器會忽略[!DNL profile.cfg]檔案的本地副本以及User\*profile name*資料夾中Dataset或Export資料夾中的任何檔案。 忽略的檔案由[!DNL User]列中的紅色背景和上下文菜單中的「在用戶目錄中忽略」警告標識。 要在這些檔案的本地副本中實施所做的更改，必須將其保存到工作配置檔案中，以便與Data Workbench伺服器同步。 有關將檔案保存到工作配置檔案的步驟，請參閱[將檔案發佈到工作配置檔案](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。
      >    
      >    
   * 連字型大小(-)（而非欄中的勾號）可識別空（零位元組）檔案。 Data Workbench將零位元組檔案視為不存在，這可讓您使用這些檔案將描述檔所包含的檔案隱藏在左側。 請參閱[使用空（零位元組）檔案隱藏檔案](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491)。


## 確定檔案版本{#section-225d732246b94cbe87acdfa9c881d6af}

如上節所述，[!DNL Profile Manager]中的複選標籤會以色碼標示，因此您可以輕鬆識別檔案的所在位置，以及是否在不同時間修改了檔案的多份副本。

如果檔案或折疊的目錄與其左側的檔案或目錄完全相同，則其顏色複選標籤與該列（配置檔案）中的檔案或目錄相同。 如果它與其左側的任何檔案或目錄不同，或者檔案或目錄僅存在於[!DNL User]列中，則複選標籤為白色。

![](assets/vis_ProfMgr_LocalFiles.png)

上述範例中的[!DNL Profile Manager]指出：

* [!DNL A New Metric.metric]檔案的白勾號只會顯示在[!DNL User]欄中，表示您只有該檔案的本機副本——尚未發佈（或上傳）至Data Workbench伺服器，供其他Data Workbench使用者存取。

* [!DNL Average Score.metric]檔案名稱的勾選標籤會出現在「影片」和「[!DNL User]」欄中。 [!DNL User]欄中的複選標籤與「影片」欄中的複選標籤顏色相同，這表示檔案的本地副本與「影片」資料夾中的檔案具有相同的「已修改」日期和時間。

* [!DNL Average Score Error.metric]檔案名稱的勾選標籤會出現在「影片」和「[!DNL User]」欄中。 [!DNL User]欄中的複選標籤為白色，表示檔案的本地副本具有與「影片」資料夾中的檔案不同的「已修改」日期或時間。

