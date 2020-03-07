---
description: 資料工作台6.0.4中引進的新功能，包括錯誤修正和已知問題。
solution: Analytics
title: 資料工作台6.0發行說明
topic: Data workbench
uuid: b348425e-3304-4db7-a280-479a34452bdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 資料工作台6.0發行說明

資料工作台6.0.4中引進的新功能，包括錯誤修正和已知問題。

## 新功能 {#section-1225066ea8f44cf68e42e019d0bca816}

資料工作台(Insight 6.0)包含這些新功能和視覺化，以新增報告功能和預測性分析工具。

| 資料工作台功能 | 說明 |
|---|---|
| [漏斗視覺化](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da) | 「漏斗」視覺化功能可讓您定義客戶的循序流程，並可洞悉流程中每個步驟的訪客流失。 |
| [訪客叢集](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d) | 叢集可讓您運用客戶特性來動態分類訪客，並根據客戶分析和定位的選取資料輸入產生叢集。 |
| [關聯分析](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c) | 關聯分析可讓您快速識別相關資料關係，以延伸並增強分析。 |
| [更新的DeviceAtlas散發](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0) | DeviceAtlas JSON檔案現在會與DeviceAtlas.dll和DeviceAtlas64.dll一起，以。bundle檔案（重新命名為。tar.gz）發佈。 |

## 用戶端升級需求 {#section-f316103b48374b6eac77e8feb5c47ecf}

完成資料工作台(Insight 6.0)用戶端功能的下列升級工作：

**更新客戶機的。zbin檔案**

資料工作台現在支援輸入法編輯器(IME)做為次要文字輸入程式，可讓您使用浮動文字方塊，從鍵盤輸入國際字元。 資料工作台預設會支援英文，但也可讓您載入其他檔案以支援國際語言，例如虛擬中文鍵盤(Piny IME)。

在更新至6.0版之前，用戶端應用程式需要新的字典檔案（.zbin檔案）。您可以從「軟體」和「檔案」描述檔（「軟體檔案」）取得所需的。zbin檔案。

必備條件:

* 在升級至Insight 6.0用戶端和Report Server 6.0之前，Insight管理員必須先升級至Insight Server 6.0。
* Insight管理員將需要根據語言(en-us.zbin, zh-cn.zbin)選擇zbin檔案、複製語言檔案，然後將其重新命名為insight.zbin，並將重新命名的檔案置於可執行檔所在之報表伺服器的根目錄中。 然後重新啟動Insight報表伺服器。

如需其他 [伺服器端升級資訊](../../../home/c-release-notes-insight/release-notes.md) ，請參閱伺服器升級需求。

**要將客戶機的zbin檔案升級（從5.x版升級到6.0版）**

1. 若要確保用戶端在此升級期間未從Insight Server取得更新，請將您的Insight.cfg引數設為false。

   ```
   Update Software = bool: false
   ```

1. 重新啟動Insight用戶端。
1. 導覽至「軟體與檔案」描述檔（SoftDocs描述檔）並下載所需的 **[!UICONTROL Insight.zbin]** 檔案： [!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. 將Insight.zbin檔案複製至與Insight.exe檔案相同的檔案夾。
1. 若要確定Insight用戶端現在從Insight Server取得更新，請將Insight.cfg檔案引數變更為true:

   ```
   Update Software = bool: true
   ```

1. 重新啟動客戶端。

   您的客戶端將與伺服器同步，您將看到一條消息，指出您的客戶端正在下載。 下載結束時，您會收到一則訊息，詢問您是否要重新啟動Insight用戶端。
1. 按一下 **確定** ，重新啟動客戶機。

   客戶端將啟動並升級至6.0版。

1. 重新啟動客戶端，Insight.zbin客戶端同步將生效。

   如果您收到下列訊息，表示zbin未放在Insight.exe檔案旁的正確資料夾位置。

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   若要修正問題，請刪除Insight.exe並將最新版Insight.exe.old重新命名為Insight.exe，然後從上述步驟1開始。

## 伺服器升級需求 {#section-d6edba8b36234957ba8d06b555667a5a}

完成Insight 6.0伺服器功能的下列升級工作：

**更新所有Insight Server 6.0套件**。 Insight 6.0包含需要更新的伺服器套件，包括新的Predictive Analytics設定檔。

>[!IMPORTANT]
>
>建議使用者在更新時升級其伺服器叢集，並安裝最新的Insight Server 6.0。

此外，建議用戶端升級其伺服器叢集，並新安裝Insight Server 6.0。

## 升級伺服器群集

**準備語言檔案（.zbin檔案）。** Insight管理員會選取 `<language>.zbin` 所需語言的檔案(例如：zh-cn.zbin)。 `/localization/<language>.zbin` 然後，管理員會複製語言檔案，並將它重新命名為「insight.zbin」。

在準備語言檔案(.zbin)後，Insight用戶端和報表伺服器都需要更新。 Insight Client會在用戶端升級程式 [中更新](../../../home/c-release-notes-insight/release-notes.md)，但在大多數情況下，Insight管理員會更新報表伺服器。

**使用語言檔案（.zbin檔案）更新報表伺服器**。

對於所有語言，Report Server 6.0需要將「insight.zbin」檔案複製至「Report Server」根資料夾。

更新報表伺服器語言檔案：

1. 將重新命名的「insight.zbin」檔案新增至根ReportServer目錄。
1. 報表伺服器設定檔案(reportserver.cfg)需要雙位元組語言的字型設定。 例如，中文需要使用SimSun添加字型：

   ```
   Report Server.cfg - Add Fonts 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Report Server 6.0的參數必須傳入命令行中，才能進行本地化，例如：

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >如果未指定地區設定，則報表伺服器會預設為insight.zbin檔案中選取的語言。

   請依照下列步驟，使用地區設定參數啟動ReportServer作為服務：

   1. 以管理員身份啟動命令提示符。
   1. 導覽至ReportServer安裝資料夾。
   1. 鍵入以下命令以啟動服務：

      * 英文版： [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * 中文： [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. 要驗證ReportServer是否使用正確的參數運行：

   1. 開啟Windows Service Manager。
   1. 按一下滑鼠右鍵 [!DNL Adobe Insight Report Server - Properties]。
   執行檔的路徑將包含以下參數：

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**修改預測性分析的描述檔設定檔**。 Insight管理員需要修改自訂profile.cfg檔案，以包含Insight中可用的Predictive Analytics描述檔。

profile.cfg項的示例：

```
Example ("profile.cfg"): 
Profile = profileInfo:  
  Active = bool: true 
  Directories = vector: 5 items 
    0 = string: Base\\  
    1 = string: Predictive Analytics\\ 
    2 = string: Geography\\ 
    3 = string: Adobe SC\\ 
    4 = string: Custom Profile\\ 
```

**更新PAServer.cfg檔案**。 如果您想要將Predictive Analytics叢集工作送出至Insight Servers，則需要設定PAServer.cfg檔案，以處理伺服器端叢集提交。

自訂描述檔應繼承Predictive Analytics描述檔(Server\Profiles\Predictive Analytics\Dataset)中的PAServer.cfg。 依您的實施網站設定並儲存PAServer.cfg。

>[!NOTE]
>
>一旦將PAServer.cfg設定並儲存至自訂描述檔，網站上就需要重新啟動Insight Server。

**升級報表伺服器。** 您需要更新報表伺服器的字型和啟動參數。

必備條件:

* 在升級Report Server 6.0之前，Insight管理員必須先升級至Insight Server 6.0。
* 對於所有語言，Report Server 6.0需要在Report Server根資料夾中新增Insight.zbin。 請確定復 `base/localization/<language>.zbin` 制後重新命名為&quot;insight.zbin&quot;。 將其複製到報表伺服器目錄的根目錄。

更新字型和啟動參數：

1. 報表伺服器需要雙位元組的字型設定，才能輸出為不同的語言。

   例如：

   報表伺服器。cfg —— 新增字型

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Report Server 6.0的參數必須傳入命令列中，才能進行本地化。

   若要以「地區設定」參數啟動「報表伺服器」作為服務：

   1. 停止報表伺服器服務。
   1. 以管理員身份啟動命令提示符。
   1. 導覽至報表伺服器安裝資料夾。
   1. 鍵入以下命令以啟動服務：

      ```
      ReportServer.exe -RegServer -Locale -en-us
      ```

要驗證報告伺服器是否使用正確的參數運行：

1. 開啟Windows Service Manager
1. 按一下滑鼠右鍵 [!DNL Adobe Insight Report Server - Properties]。
1. 執行檔的路徑將包含以下參數：

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**升級Insight 6.0的SiteCatalyst資料饋送**。 Insight 6.0的SiteCatalyst資料饋送檔案名稱格式已變更。

目前檔案名稱格式：

```
 RSID_YYYYMMDD_HH0000.tsv.gz
```

新檔案名稱格式：

```
YYYYMMDD-RSID_HH0000.tsv.gz
```

>[!NOTE]
>
>此變更不會影響目前與SiteCatalyst資料饋送 *wbench/ecom版本一起部署* 的使用者。

檔案名稱格式變更可讓您在記錄處理期間完全使用Insight開始和結束時間宣告。 這可讓程式評估是否應讀取檔案的內容，而不是使用逐行搜索來過濾所有源檔案。

在大多數情況下，在收到檔案時會實施重新命名程式，以充份運用此功能。 預設情況下，此修改提供了所需的命名約定，而無需輔助進程的需要和開銷。

若要使用新的SiteCatalyst資料饋送：

1. 確定接收進程如何處理新的檔案名格式。

   實作期間部署的標準重新命名／移動指令碼會移動副檔名為&quot;。gz&quot;的檔案，而且只有在檔案名稱符合檔案名稱格式與前述RSID時，才會執行重新命名。

   新的檔案名稱格式：

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. 評估定義的日誌源路徑，以確認將讀取所有檔案。

   如果您已實作重新命名指令碼，則您已定義記錄檔來源以讀取此新檔案名稱格式。

## 修正 {#section-203f917dd6224114a1f801309c4c2cee}

* 現在，離開工作區而不儲存變更的關鍵組合已更新為 **[!UICONTROL `<Ctrl>`+`<Backspace>`]**。 以前，您可以按+來撤消更改並關閉工`<Ctrl>`作區`<Delete>`。

## Data Workbench 6.0.4 Release Notes{#data-workbench-release-notes}

資料工作台6.0.4中引進的新功能，包括錯誤修正和已知問題。

若要檢視每個過去版本的先前功能和修正，請參閱版 [本說明封存](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html)。

## 新功能 {#section-2-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.0.4包含這些新功能和視覺化，以新增報告功能和預測性分析工具。

**傾向得分視覺化**。 資料工作台會計算每位訪客的分數，作為指定事件可能發生的估計可能性。 「訪客計分」視覺化可讓您建立分數維度，根據輸入變數為每個感興趣的訪客提供指定事件的概率。

![](assets/visitor_scoring_visual.png)

如需 [此功能的詳細資訊](../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-visitor-propensity.md#concept-2958f4640dd44b9d86ad51c4f6165f40) ，請參閱傾向評分。

## 升級需求 {#section-08bd6fe3da8740fcb19688e8cac6f223}

**必須定義日誌源ID**。 從6.04版開始，如果未定義記錄來源ID，則會出現下列錯誤：

```
Missing Log Souce ID in log processing.cfg. Log Source ID must be  
defined for all log sources.
```

「記錄每個記錄來源的列」已新增至資料工作台6.0，並可透過新增唯一名稱的「記錄來源ID」，在自訂描述檔Log Processing.cfg中定義。 如果您有空白的「記錄來源ID」，則會看到「記錄處理」問題，例如記錄來源資料的讀取不完整及其他不一致。

```
Log Processing.cfg 
Log Sources = vector: 2 items 
  0 = VisualSensor: 
    Compressed = bool: false 
    Log Paths = vector: 1 items 
      0 = Path: \some path\ 
    Log Server = serverInfo:  
      Address = string:  
      Name = string:  
      Port = int: 80 
      Proxy Address = string:  
      Proxy Password = string:  
      Proxy Port = int: 8080 
      Proxy User Name = string:  
      SSL Client Certificate = string: Certificates\\server_cert.pem 
      SSL Server Common Name = string:  
      Use SSL = bool: false 
     
Log Source ID = string: <Name your ID Here>
    Name = string:  
    Recursive = bool: false
```

**可委派FSU資源**

在 [!DNL Profiles/`<profilename>`/dataset/Cluster.cfg]，您現在可以為標準化和來源清單伺服器指定個別的檔案伺服器單位(FSU)。 這些服務不再與主FSU綁定。

>[!NOTE]
>
>如果未指定清單伺服器，則清單伺服器將繼承標準化伺服器的配置設定。

Example in the [!DNL cluster.cfg] file.

```
Cluster = ClusterConfig: 
  Normalize Server = serverInfo: 
    Address = string: normalizeserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false 
  List Server = serverInfo: 
    Address = string: sourcelistserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false
```

## 修正的錯誤 {#section-3b4b85a35f534288adf8a5246ef028cc}

* 在Data Workbench 6.0中，關聯矩陣和叢集產生器不支援「在背景計算」。 這在6.0.4版中已修正。
* 以前，如果您在漏斗上有選擇並移除步驟，可能會發生存取違規。 這個問題已經解決。
* 已修正「區段匯出」中可能在重負載條件下造成問題的潛在鎖定條件。
