---
description: 實施中包含的資料夾和檔案名稱會顯示在「設定檔管理員」的左側。
title: 設定檔管理員
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# 設定檔管理員{#profile-manager}

實施中包含的資料夾和檔案名稱會顯示在「設定檔管理員」的左側。

組成您的應用程式的設定檔會顯示為[!DNL Profile Manager]中的個別欄。 這些設定檔包含多個繼承的設定檔和單一工作設定檔。

>[!NOTE]
>
>工作設定檔（資料集設定檔或角色專屬設定檔）是您開啟Data Workbench時載入的設定檔。

勾號（及其顏色）指示每個檔案所在的Data Workbench伺服器和Data Workbench電腦上的配置檔案資料夾、檔案是否存在多個副本，以及這些多個副本是否具有相同的修改日期和時間。 在配置檔案下載期間，這些檔案會在Data Workbench伺服器和Data Workbench電腦之間同步。

以下是HBX實作的範例[!DNL Profile Manager]:

![](assets/client-prof.png)

從[!DNL Profile Manager]菜單中，可以開啟任何其它管理器（例如[!DNL Dimensions Manager]或[!DNL Reports Manager]），這些管理器只顯示[!DNL Profile Manager]的特定部分。 您也可以建立新的設定檔管理員。 請參閱[建立新的配置檔案管理器](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3)。

特定列中檔案名旁的複選標籤表示該名稱的檔案位於該列（配置檔案）中名為的資料夾中。 在[!DNL Profile Manager]中，當您移至右側時，檔案優先於左側的檔案，也就是說，每個繼承的配置檔案都建立在[!DNL Profile Manager]中左側的配置檔案上。 例如，如果在[!DNL Base]配置檔案（列）和[!DNL User]配置檔案（列）中，檔案名稱相同且位於相同位置，則會使用[!DNL User]配置檔案中的檔案，而不是[!DNL Base]配置檔案中的檔案。

## 搜尋設定檔{#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

使用Data Workbench5.5時，已新增搜尋欄位，以在[!DNL Profile Manager]中尋找必要的設定檔。

![](assets/client-prof2.png)

[!DNL Profile Manager]中顯示的列類型如下：

* *繼承的配置檔案名稱*&#x200B;列包含駐留在每個配置檔案資料夾中的檔案的勾號。 繼承的設定檔包括Adobe提供的內部設定檔，以及您建立和維護的任何公司專屬或角色專屬設定檔。 在上述範例中，內部設定檔包括基礎、流量、值、行銷等。 每個實施都會提供內部[!DNL Base]設定檔，其中包含執行Adobe應用程式所需的基本建置區塊和設定資訊。 其他內部設定檔包含與特定資訊類型（例如網路流量或行銷）相關的元素（工作區、量度、衍生維度等）。 Adobe僅提供適用於您所分析資料類型和您所在行業的設定檔。

   >[!NOTE]
   >
   >依預設，無法變更內部設定檔(由Adobe提供的設定檔)。 所有自訂都必須發生在您的資料集、角色專屬設定檔或您建立的其他設定檔中。 如果您正在構建新應用程式並且需要更改內部配置檔案，則必須更改[!DNL Insight.cfg]檔案中的修改內部配置檔案參數。 如需詳細資訊，請參閱[分析設定參數](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) 。 在此之前，請連絡Adobe諮詢服務。

* *工作設定檔名稱*&#x200B;欄（一律為倒數第二欄）包含存放在目前工作設定檔資料夾中之檔案的勾號。 在上述範例中，工作設定檔為資料集。 您的工作設定檔是資料集設定檔或角色專屬設定檔。 此資料夾中的檔案優先於任何繼承的配置檔案資料夾中名稱相同的檔案。
* [!DNL User]列始終是最後一列，它包含對User\*profile name*資料夾中作為本地檔案的檔案和資料夾的檢查標籤。 「用戶」資料夾的目錄結構與工作配置檔案的目錄結構類似，每個「用戶\*配置檔案名稱*」資料夾都包含該特定配置檔案的工作區、度量、維和配置檔案的本地副本。 這些本地副本優先於任何繼承或工作配置檔案資料夾中名稱相同的檔案。 [!DNL User]列中的檔案已建立並僅保存到User\*profile name*資料夾中，或者它們位於內部或工作配置檔案中，以及User\*profile name*資料夾中。 每個資料夾中的檔案可能相同，也可能不相同，並且可能具有或不具有相同的修改日期和時間。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 為了避免僅在本地更改您的資料集，Data Workbench伺服器會忽略[!DNL profile.cfg]檔案的本地副本以及User\*profile name*資料夾中「資料集」或「導出」資料夾中的任何檔案。 忽略的檔案在[!DNL User]欄中以紅色背景標識，在上下文菜單中以「在用戶目錄中忽略」警告標識。 若要在這些檔案的本機副本中實作您所做的變更，您必須將變更儲存至工作設定檔，以便與Data Workbench伺服器同步。 有關將檔案保存到工作配置檔案的步驟，請參閱[將檔案發佈到工作配置檔案](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。
      >    
      >    
   * 連字型大小(-)（而非欄中的勾號）代表空白（零位元組）檔案。 Data Workbench將零位元組檔案視為不存在，這可讓您使用它們來隱藏包含在左側設定檔中的檔案。 請參閱[使用空（零位元組）檔案隱藏檔案](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491)。


## 確定檔案版本{#section-225d732246b94cbe87acdfa9c881d6af}

如前一節所述，[!DNL Profile Manager]中的複選標籤用彩色編碼，這樣您就可以輕鬆識別檔案的駐留位置，以及是否在不同時間修改了檔案的多個副本。

如果檔案或折疊的目錄與其左側的檔案或目錄完全相同，則其顏色複選標籤與該列（配置檔案）中的檔案或目錄相同。 如果與其左側的任何檔案或目錄不同，或檔案或目錄僅存在於[!DNL User]列中，則複選標籤為白色。

![](assets/vis_ProfMgr_LocalFiles.png)

上例所示的[!DNL Profile Manager]指示以下內容：

* [!DNL A New Metric.metric]檔案的白勾號僅顯示在[!DNL User]欄中，表示您只有該檔案的本機副本 — 該副本尚未發佈（或上傳）至Data Workbench伺服器，供其他Data Workbench使用者存取。

* [!DNL Average Score.metric]檔案名的勾號會出現在「電影」和[!DNL User]欄中。 [!DNL User]列中的複選標籤顏色與「電影」列中的複選標籤顏色相同，表示檔案的本地副本與「電影」資料夾中的檔案具有相同的「已修改」日期和時間。

* [!DNL Average Score Error.metric]檔案名的勾號會出現在「電影」和[!DNL User]欄中。 [!DNL User]列中的複選標籤為白色，表示檔案的本地副本具有與「電影」資料夾中的檔案不同的「已修改」日期或時間。

