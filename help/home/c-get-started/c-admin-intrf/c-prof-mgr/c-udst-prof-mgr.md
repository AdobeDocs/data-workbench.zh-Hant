---
description: 實施中包含的資料夾和檔案名稱會顯示在「設定檔管理員」的左側。
title: 設定檔管理員
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# 設定檔管理員{#profile-manager}

{{eol}}

實施中包含的資料夾和檔案名稱會顯示在「設定檔管理員」的左側。

組成您應用程式的設定檔會顯示為 [!DNL Profile Manager]. 這些設定檔包含多個繼承的設定檔和單一工作設定檔。

>[!NOTE]
>
>工作設定檔（資料集設定檔或角色專屬設定檔）是您開啟Data Workbench時載入的設定檔。

勾號（及其顏色）指示每個檔案所在的Data Workbench伺服器和Data Workbench電腦上的配置檔案資料夾、檔案是否存在多個副本，以及這些多個副本是否具有相同的修改日期和時間。 在配置檔案下載期間，這些檔案會在Data Workbench伺服器和Data Workbench電腦之間同步。

以下是範例 [!DNL Profile Manager] 若為HBX實作：

![](assets/client-prof.png)

從 [!DNL Profile Manager] 功能表，您可以開啟任何其他管理器(例如 [!DNL Dimensions Manager] 或 [!DNL Reports Manager])，只會顯示 [!DNL Profile Manager]. 您也可以建立新的設定檔管理員。 請參閱 [建立新的配置檔案管理器](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3).

特定列中檔案名旁的複選標籤表示該名稱的檔案位於該列（配置檔案）中名為的資料夾中。 當您移至 [!DNL Profile Manager]，檔案優先於左側的檔案，亦即每個繼承的設定檔都以位於左側的設定檔為基礎 [!DNL Profile Manager]. 例如，若檔案的名稱相同，且位於 [!DNL Base] 設定檔（欄）和 [!DNL User] 設定檔（欄）中的檔案 [!DNL User] 會使用設定檔，而非 [!DNL Base] 設定檔。

## 搜尋設定檔 {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

使用Data Workbench5.5時，已新增搜尋欄位，以在 [!DNL Profile Manager].

![](assets/client-prof2.png)

下列類型的欄會顯示在 [!DNL Profile Manager]:

* 此 *繼承的設定檔名稱* 列包含駐留在每個配置檔案資料夾中的檔案的檢查標籤。 繼承的設定檔包括Adobe提供的內部設定檔，以及您建立和維護的任何公司專屬或角色專屬設定檔。 在上述範例中，內部設定檔包括基礎、流量、值、行銷等。 內部 [!DNL Base] 每個實施都會提供設定檔，其中包含執行Adobe應用程式所需的基本建置區塊和設定資訊。 其他內部設定檔包含與特定資訊類型（例如網路流量或行銷）相關的元素（工作區、量度、衍生維度等）。 Adobe僅提供適用於您所分析資料類型和您所在行業的設定檔。

   >[!NOTE]
   >
   >依預設，無法變更內部設定檔(由Adobe提供的設定檔)。 所有自訂都必須發生在您的資料集、角色專屬設定檔或您建立的其他設定檔中。 如果您要建立新應用程式且需要變更內部設定檔，您必須在 [!DNL Insight.cfg] 檔案。 請參閱 [分析設定參數](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) 以取得更多資訊。 在此之前，請連絡Adobe諮詢服務。

* 此 *工作設定檔名稱* 列（始終為倒數列）包含駐留在當前工作配置檔案資料夾中的檔案的複選標籤。 在上述範例中，工作設定檔為資料集。 您的工作設定檔是資料集設定檔或角色專屬設定檔。 此資料夾中的檔案優先於任何繼承的配置檔案資料夾中名稱相同的檔案。
* 此 [!DNL User] 列（始終是最後一列）包含對User\*profile name*資料夾中作為本地檔案的檔案和資料夾的複選標籤。 「用戶」資料夾的目錄結構與工作配置檔案的目錄結構類似，每個「用戶\*配置檔案名稱*」資料夾都包含該特定配置檔案的工作區、度量、維和配置檔案的本地副本。 這些本地副本優先於任何繼承或工作配置檔案資料夾中名稱相同的檔案。 中的檔案 [!DNL User] 列被建立並保存到「用戶\*配置檔案名稱*」資料夾，或者它們位於內部或工作配置檔案以及「用戶\*配置檔案名稱*」資料夾中。 每個資料夾中的檔案可能相同，也可能不相同，並且可能具有或不具有相同的修改日期和時間。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 為了避免僅在本機變更資料集，Data Workbench伺服器會忽略 [!DNL profile.cfg] 檔案和「資料集」或「匯出」資料夾中的任何檔案。 忽略的檔案是以 [!DNL User] 欄和內容功能表中的「在使用者目錄中忽略」警告。 若要在這些檔案的本機副本中實作您所做的變更，您必須將變更儲存至工作設定檔，以便與Data Workbench伺服器同步。 如需將檔案儲存至工作設定檔的步驟，請參閱 [將檔案發佈至工作設定檔](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
   >    
   >    * 連字型大小(-)（而非欄中的勾號）代表空白（零位元組）檔案。 Data Workbench將零位元組檔案視為不存在，這可讓您使用它們來隱藏包含在左側設定檔中的檔案。 請參閱 [使用空（零位元組）檔案隱藏檔案](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491).


## 確定檔案版本 {#section-225d732246b94cbe87acdfa9c881d6af}

如前一節所述， [!DNL Profile Manager] 會以色碼編碼，以便您可以輕鬆識別檔案所在的位置，以及是否在不同時間修改了檔案的多個副本。

如果檔案或折疊的目錄與其左側的檔案或目錄完全相同，則其顏色複選標籤與該列（配置檔案）中的檔案或目錄相同。 如果它與其左側的任何檔案或目錄不同，或檔案或目錄僅存在於 [!DNL User] 欄中，複選標籤為白色。

![](assets/vis_ProfMgr_LocalFiles.png)

此 [!DNL Profile Manager] 如上例所示，表示下列項目：

* 的白色勾號 [!DNL A New Metric.metric] 檔案僅顯示在 [!DNL User] 欄，表示您只有該檔案的本機副本 — 尚未發佈（或上傳）至Data Workbench伺服器，供其他Data Workbench使用者存取。

* 的勾號 [!DNL Average Score.metric] 檔案名顯示在「電影」和 [!DNL User] 欄。 中的勾號 [!DNL User] 列的顏色與「電影」列中的複選標籤相同，表示檔案的本地副本與「電影」資料夾中的檔案具有相同的「已修改」日期和時間。

* 的勾號 [!DNL Average Score Error.metric] 檔案名顯示在「電影」和 [!DNL User] 欄。 中的勾號 [!DNL User] 列為白色，表示檔案的本地副本具有與「影片」資料夾中的檔案不同的「已修改」日期或時間。

