---
description: 在「記錄處理資料集」中定義的網頁特定設定資訊，包括與網站的Adobe設定檔一起傳送的檔案。
solution: Analytics
title: 用於日誌處理的Web特定設定
topic: Data workbench
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 用於日誌處理的Web特定設定{#web-specific-settings-for-log-processing}

在「記錄處理資料集」中定義的網頁特定設定資訊，包括與網站的Adobe設定檔一起傳送的檔案。

由這些設定定義的過濾發生在日誌條目離開解碼器之後，並且變換被應用，但在由評估之前 [!DNL Log Entry Condition]。

* [HTTP狀態篩選](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [機器人過濾](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## HTTP狀態篩選 {#section-ac66acdcb6aa467d81c3721199e540fd}

您可以設定您的實作， [!DNL Site] 從資料集中移除sc-status代碼為400或更高的記錄項目。 成功的請求的狀態代碼小於400。 您的預設實作包含 [!DNL Log Processing Dataset Include] 已設定HTTP狀態篩選的檔案。

**要編輯HTTP狀態過濾的配置設定**

1. 在資料集 [!DNL Profile Manager] 設定檔中開啟，並開啟 [!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg] 檔案。

   >[!NOTE]
   >
   >如果您已自訂實作， [!DNL Site]則這些組態設定所在的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯檔案參數的值。 以下範例為指南。

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   有關該條件的信 [!DNL Range] 息，請參 [閱條件](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。

1. 以滑鼠 [!DNL HTTP Status Filter.cfg] 右鍵按一下視窗上 **[!UICONTROL (modified)]** 方的滑鼠右鍵並按一下，以儲存檔案 **[!UICONTROL Save]**。

1. 若要讓本機所做的變更生效，請在欄中 [!DNL Profile Manager]，以滑鼠右鍵按一下該檔案的核取標籤，然後按一下 [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***，其中描述檔名稱是資料集描述檔的名稱或資料集包含檔案所屬的繼承描述檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

## 機器人過濾 {#section-7f43681dfbc64b969619cb88f97d5ad5}

您可以設定您的實作，使 [!DNL Site] 用查閱檔案從資料集中移除由已知自動機產生的記錄項目、測試指令碼和內部使用者的IP位址。 您的預設實作包含 [!DNL Log Processing Dataset Include] 已設定自動機篩選的檔案。

**要編輯用於自動機過濾的配置設定，請執行以下操作：**

1. 在資料集 [!DNL Profile Manager] 設定檔中開啟，並開啟 [!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg] 檔案。

   >[!NOTE]
   >
   >如果您已自訂實作， [!DNL Site]則這些組態設定所在的檔案可能與描述的位置不同。

1. 使用下列範例和資訊作為參考線，檢視或編輯檔案的參數：

   ![](assets/cfg_WebParameters_RobotFilter.png)

   該檔案包含 [!DNL NotRobotCondition] 由以下三個參數定義的參數：

   * **不區分大小寫的自動機過濾：** 是非。 如果為true，則在自動機過濾中不考慮字母大小寫（上／下）。
   * **自動查找檔案，基線：** 文本檔案的路徑和檔案名，該文本檔案包含已知的自動機瀏覽器用戶代理的清單，並將從資料集中過濾出來。 Adobe提供基線自動機查閱檔案。 如果您未指定路徑，資料工作台伺服器會在資料工作台伺服器安裝目錄的「查閱」目錄中尋找此檔案。
   * **自動查找檔案，擴展：** 可選文本檔案的路徑和檔案名，其中包含瀏覽器用戶代理或IP地址清單，這些地址定義特定於您的實施的自動機。 此清單可包含內部監控自動機、測試指令碼，以及應從資料集中篩選的內部使用者的IP位址。 如果您未指定路徑，資料工作台伺服器會在資料工作台伺服器安裝目錄的「查閱」目錄中尋找此檔案。
   如果某個記錄項目的瀏覽器使用者代理未列在任一查閱檔案中，則該記錄項目會被視為由實際訪客產生，且不會從資料集中篩選。

   >[!NOTE]
   >
   >自動機查閱檔案中的比對使用子字串來比較c-ip和cs(user-agent)記錄檔欄位。 如果搜尋字串以&quot;$&quot;開頭，則必須符合正在測試的字串前方，如果結尾為&quot;$&quot;，則搜尋字串必須符合正在測試的字串結尾。 如果搜尋字串皆以&quot;$&quot;開頭和結尾，則字串必須完全符合，才能篩選出記錄項目。 例如，要測試C類塊中的所有IP地址，您應使用一個字串，如$231.78.123。在字串前面強制匹配。 這會比對地址231.78.123.0到231.78.123.255。

1. 以滑鼠右鍵按一下視窗頂 **[!UICONTROL (modified)]** 端的檔案，然後按一下以儲存檔案 **[!UICONTROL Save]**。

1. 若要讓本機所做的變更生效，請在欄中 [!DNL Profile Manager]，以滑鼠右鍵按一下該檔案的核取標籤，然後按一下 [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***，其中描述檔名稱是資料集描述檔的名稱或資料集包含檔案所屬的繼承描述檔。

   請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

   >[!NOTE]
   >
   >如果用於構建資料集的基礎日誌條目沒有更改（即使用於構建和更新資料集的轉換及其尺寸有所更改），則應控製版本。 在這些檔案上放置版本號碼可確保對預設自動機查閱檔案的更新不會透過新增或刪除這些檔案中的項目，無意中變更先前建立的報表資料集。

