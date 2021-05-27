---
description: Data Workbench6.0.4推出的新功能，包括錯誤修正和已知問題。
title: Data Workbench 6.0 發行說明
uuid: b348425e-3304-4db7-a280-479a34452bdb
exl-id: be69b3be-24e7-4a8c-9dc8-1360a9b6fb3a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1679'
ht-degree: 2%

---

# Data Workbench 6.0 發行說明

Data Workbench6.0.4推出的新功能，包括錯誤修正和已知問題。

## 新特性 {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench(Insight 6.0)包含這些新功能和視覺效果，以新增報表功能和預測分析工具。

| Data Workbench功能 | 說明 |
|---|---|
| [漏斗視覺效果](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da) | 漏斗視覺效果可讓您定義客戶的循序流程，並可顯示流程中每個步驟的訪客流失。 |
| [訪客叢集](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d) | 叢集可讓您運用客戶特性，以動態方式分類訪客，並根據客戶分析和鎖定目標所選資料輸入產生叢集。 |
| [關聯分析](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c) | 關聯分析可讓您快速識別相關資料關係，以擴充和增強您的分析。 |
| [更新DeviceAtlas發佈](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0) | DeviceAtlas JSON檔案現在將以.bundle檔案（重新命名為.tar.gz）及DeviceAtlas.dll和DeviceAtlas64.dll分發。 |

## 客戶端升級要求{#section-f316103b48374b6eac77e8feb5c47ecf}

完成Data Workbench(Insight 6.0)用戶端功能的下列升級工作：

**更新客戶端的.zbin檔案**

Data Workbench現在支援輸入法編輯器(IME)作為次要文字輸入程式，可讓您使用浮動文字方塊從鍵盤輸入國際字元。 Data Workbench預設會支援英文，但也可讓您載入其他檔案以支援國際語言，例如虛擬中文鍵盤（拼音輸入法）。

客戶端應用程式在更新到6.0版之前需要新的字典檔案（.zbin檔案）。您可以從軟體和文檔配置檔案（軟體文檔）中獲取所需的.zbin檔案。

先決條件:

* 在升級至Insight 6.0用戶端和Report Server 6.0之前，Insight管理員必須先升級至Insight Server 6.0。
* Insight管理員將需要根據語言(en-us.zbin、zh-cn.zbin)選擇zbin檔案，複製該語言檔案，然後將其重新命名為insight.zbin，並將重新命名的檔案置於執行檔所在之報表伺服器的根目錄中。 然後重新啟動Insight報表伺服器。

如需其他伺服器端升級資訊，請參閱[伺服器升級需求](../../../home/c-release-notes-insight/release-notes.md) 。

**將客戶端的zbin檔案升級（從5.x版升級到6.0版）**

1. 若要確認在此升級期間用戶端未從Insight Server更新，請將Insight.cfg引數設為false。

   ```
   Update Software = bool: false
   ```

1. 重新啟動Insight用戶端。
1. 導覽至「軟體」和「檔案」設定檔（SoftDocs設定檔），然後下載必要的&#x200B;**[!UICONTROL Insight.zbin]**&#x200B;檔案：[!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. 將Insight.zbin檔案複製至與Insight.exe檔案相同的資料夾。
1. 若要確認Insight用戶端現在已從Insight Server更新，請將Insight.cfg檔案引數變更為true:

   ```
   Update Software = bool: true
   ```

1. 重新啟動客戶端。

   您的客戶端將與伺服器同步，您將看到一條消息，指明您的客戶端正在下載。 下載結束時，您會收到訊息，詢問您是否要重新啟動Insight用戶端。
1. 按一下&#x200B;**OK**&#x200B;重新啟動客戶端。

   客戶端將啟動並升級到6.0版。

1. 重新啟動用戶端，讓Insight.zbin用戶端同步生效。

   如果您收到下列訊息，表示zbin未放置在Insight.exe檔案旁的正確資料夾位置。

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   若要修正問題，請刪除Insight.exe並將最新版Insight.exe.old重新命名為Insight.exe，然後從上述步驟1重新開始。

## 伺服器升級要求{#section-d6edba8b36234957ba8d06b555667a5a}

完成Insight 6.0伺服器功能的以下升級工作：

**更新所有Insight Server 6.0套件**。Insight 6.0包含需要更新的伺服器套件，包括新的預測分析設定檔。

>[!IMPORTANT]
>
>建議使用者在更新時，使用全新安裝的Insight Server 6.0來升級其伺服器叢集。

此外，建議用戶端透過全新安裝Insight Server 6.0來升級其伺服器叢集。

## 升級伺服器群集

**準備語言檔案（.zbin檔案）。** Insight管理員會選取 `<language>.zbin` 所需語言的檔案(例如：en-us.zbin 、 zh-cn.zbin)位於資料夾 `/localization/<language>.zbin` 中。然後，管理員會複製語言檔案，並將其重新命名為「insight.zbin」。

準備語言檔案(.zbin)後，Insight Client和Report Server都需要更新。 Insight Client會在[用戶端升級程式](../../../home/c-release-notes-insight/release-notes.md)期間更新，但在大多數情況下，Insight管理員會更新報表伺服器。

**使用語言檔案（.zbin檔案）更新報表伺服器**。

對於所有語言， Report Server 6.0需要複製到Report Server根資料夾的「insight.zbin」檔案。

更新報表伺服器語言檔案：

1. 將重新命名的「insight.zbin」檔案新增至根ReportServer目錄。
1. Report Server配置檔案(reportserver.cfg)需要雙位元組語言的字型設定。 例如，中文要求使用SimSun添加字型：

   ```
   Report Server.cfg - Add Fonts 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. 報表伺服器6.0的參數需要傳入命令列才能進行本地化，例如：

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >如果未指定地區設定，則報表伺服器預設為insight.zbin檔案中選取的語言。

   按照步驟以使用Locale參數啟動ReportServer as a服務：

   1. 以管理員身分啟動命令提示。
   1. 導覽至ReportServer安裝資料夾。
   1. 鍵入以下命令以啟動服務：

      * 英語：[!DNL ReportServer.exe -RegServer -Locale -en-us]
      * 中文：[!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. 要驗證ReportServer是否使用正確的參數運行，請執行以下操作：

   1. 開啟Windows服務管理器。
   1. 按一下右鍵[!DNL Adobe Insight Report Server - Properties]。

   執行檔的路徑將包含下列參數：

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**修改預測分析的設定檔設定檔案**。Insight管理員需要修改自訂profile.cfg檔案，以包含要在Insight中使用的Predictive Analytics設定檔。

profile.cfg項目範例：

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

**更新PAServer.cfg檔案**。如果您想要將Predictive Analytics叢集作業提交至Insight Server，則需要設定PAServer.cfg檔案，以處理伺服器端叢集提交。

自訂設定檔應繼承Predictive Analytics設定檔(Server\Profiles\Predictive Analytics\Dataset)中的PAServer.cfg。 根據您的實作網站設定並儲存PAServer.cfg。

>[!NOTE]
>
>在配置PAServer.cfg並將其保存到自定義配置檔案後，整個站點都需要重新啟動Insight Server。

**升級報表伺服器。** 您需要更新報表伺服器的字型和啟動參數。

先決條件:

* 升級Report Server 6.0之前，Insight管理員必須先升級至Insight Server 6.0。
* 對於所有語言， Report Server 6.0需要在Report Server根資料夾中新增Insight.zbin。 確認已複製`base/localization/<language>.zbin`並將其重新命名為「insight.zbin」。 將其複製到報表伺服器目錄的根目錄中。

更新字型和啟動參數：

1. 報表伺服器需要雙位元組的字型設定，才能輸出至不同的語言。

   例如：

   Report Server.cfg — 新增字型

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. 報表伺服器6.0的參數必須傳入命令列，才能進行本地化。

   要使用區域設定參數啟動Report Server服務，請執行以下操作：

   1. 停止報表伺服器服務。
   1. 以管理員身分啟動命令提示。
   1. 導覽至報表伺服器安裝資料夾。
   1. 鍵入以下命令以啟動服務：

      ```
      ReportServer.exe -RegServer -Locale -en-us
      ```

驗證報表伺服器是否使用正確的參數運行：

1. 開啟Windows服務管理器
1. 按一下右鍵[!DNL Adobe Insight Report Server - Properties]。
1. 執行檔的路徑將包含下列參數：

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**升級Insight 6.0的SiteCatalyst資料摘要**。Insight 6.0SiteCatalyst資料摘要的檔案名稱格式已變更。

當前檔案名格式：

```
 RSID_YYYYMMDD_HH0000.tsv.gz
```

新檔案名格式：

```
YYYYMMDD-RSID_HH0000.tsv.gz
```

>[!NOTE]
>
>此變更不會影響目前與&#x200B;*wbench/ecom*&#x200B;版本的SiteCatalyst資料饋送一併部署的使用者。

檔案名稱格式變更可讓您在記錄處理期間完整使用Insight開始和結束時間宣告。 這使進程能夠評估是否應讀取檔案的內容，而不是使用逐行搜索來篩選所有源檔案。

在大多數情況下，在收到檔案時會實施更名過程，以充分利用此功能。 預設情況下，此修改提供所需的命名慣例，無需輔助進程的需要和開銷。

若要使用新的SiteCatalyst資料摘要：

1. 確定接收過程如何處理新的檔案名格式。

   實作期間部署的標準重新命名/移動指令碼會移動副檔名為「.gz」的檔案，且只有在檔案名稱符合檔案名稱格式與先前的RSID時才會執行重新命名。

   新的檔案名格式：

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. 評估定義的日誌源路徑，以確認將讀取所有檔案。

   如果已實施更名指令碼，則已定義日誌源以讀取此新檔案名格式。

## 修正項目 {#section-203f917dd6224114a1f801309c4c2cee}

* 現在，離開工作區而不儲存變更的關鍵組合已更新為&#x200B;**[!UICONTROL `<Ctrl>`+`<Backspace>`]**。 以前，您可以按`<Ctrl>` + `<Delete>`取消變更並關閉工作區。

## Data Workbench 6.0.4 發行說明{#data-workbench-release-notes}

Data Workbench6.0.4推出的新功能，包括錯誤修正和已知問題。

若要檢視每個過去版本的先前功能和修正，請參閱[發行說明封存檔](https://docs.adobe.com/content/help/zh-Hant/data-workbench/using/release-notes/release-notes.translate.html)。

## 新特性 {#section-2-1225066ea8f44cf68e42e019d0bca816}

Data Workbench6.0.4包含這些新功能和視覺效果，可讓您新增報表功能和預測分析工具。

**傾向分數視覺效果**。Data Workbench會以指定事件可能發生的預估機率來計算每位訪客的分數。 「訪客分數」視覺效果可讓您建立分數維度，根據輸入變數為每個感興趣的訪客提供指定事件的機率。

![](assets/visitor_scoring_visual.png)

如需此功能的其他資訊，請參閱[傾向分數](../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-visitor-propensity.md#concept-2958f4640dd44b9d86ad51c4f6165f40)。

## 升級需求 {#section-08bd6fe3da8740fcb19688e8cac6f223}

**必須定義記錄來源ID**。從6.04版開始，如果未定義記錄來源ID，您會收到下列錯誤：

```
Missing Log Souce ID in log processing.cfg. Log Source ID must be  
defined for all log sources.
```

Data Workbench6.0新增了「每個記錄來源的列記錄」 ，並可借由新增唯一名稱的「記錄來源ID」，在自訂設定檔Log Processing.cfg中定義。 如果您有空白的記錄來源ID，則會看到記錄處理問題，例如記錄來源資料的讀取不完整及其他差異。

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

**委派FSU資源的功能**

在[!DNL Profiles/`<profilename>`/dataset/Cluster.cfg]中，您現在可以為標準化和源清單伺服器指定單獨的檔案伺服器單元(FSU)。 這些服務不再與主FSU系結。

>[!NOTE]
>
>如果未指定清單伺服器，則清單伺服器將繼承標準化伺服器的配置設定。

[!DNL cluster.cfg]檔案中的範例。

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

* 在Data Workbench6.0中，關聯矩陣和叢集產生器不支援背景中的計算。 6.0.4版已修正此問題。
* 以前，如果您在漏斗上選取並移除步驟，可能會發生存取違規。 此問題已解決。
* 修正「區段匯出」中可能在重負載條件下造成問題的鎖定條件。
