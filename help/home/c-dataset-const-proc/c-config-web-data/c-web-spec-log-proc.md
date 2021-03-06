---
description: 記錄處理資料集包含檔案中定義之特定網頁設定的相關資訊，這些檔案會隨網站的Adobe設定檔傳送。
title: 記錄處理的 Web 專屬設定
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
exl-id: abb6e6a7-011f-40d6-b778-16da2332af72
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# 記錄處理的 Web 專屬設定{#web-specific-settings-for-log-processing}

記錄處理資料集包含檔案中定義之特定網頁設定的相關資訊，這些檔案會隨網站的Adobe設定檔傳送。

由這些設定定義的過濾在日誌條目離開解碼器並應用轉換之後，但在[!DNL Log Entry Condition]評估之前。

* [HTTP狀態篩選](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [機器人過濾](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## HTTP狀態篩選{#section-ac66acdcb6aa467d81c3721199e540fd}

您可以設定[!DNL Site]實作，從資料集中移除sc-status代碼為400或更新的記錄項目。 成功的請求的狀態代碼小於400。 您的預設實作包含[!DNL Log Processing Dataset Include]檔案，其中已設定HTTP狀態篩選。

**編輯HTTP狀態篩選的配置設定**

1. 在資料集設定檔中開啟[!DNL Profile Manager]，並開啟[!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg]檔案。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]實作，則存在這些組態設定的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯檔案參數的值。 請使用下列範例作為指南。

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   有關[!DNL Range]條件的資訊，請參閱[條件](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存[!DNL HTTP Status Filter.cfg]檔案。

1. 若要讓本機所做的變更生效，請在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中檔案的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***，其中，設定檔名稱是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

## 機器人過濾{#section-7f43681dfbc64b969619cb88f97d5ad5}

您可以設定[!DNL Site]實作，以使用查閱檔案來移除已知機器人、測試指令碼和資料集內內部使用者IP位址所產生的記錄項目。 預設實施包含[!DNL Log Processing Dataset Include]檔案，其中配置了自動機篩選。

**要編輯自動過濾的配置設定，請執行以下操作**

1. 在資料集設定檔中開啟[!DNL Profile Manager]，並開啟[!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg]檔案。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]實作，則存在這些組態設定的檔案可能與描述的位置不同。

1. 使用以下示例和參考資訊查看或編輯檔案的參數：

   ![](assets/cfg_WebParameters_RobotFilter.png)

   此檔案包含[!DNL NotRobotCondition]，由下列三個參數定義：

   * **不區分大小寫的機器人過濾：** True或False。如果為true，則在自動過濾中不會考慮字母大小寫（上/下）。
   * **自動查找檔案，基線：** 文本檔案的路徑和檔案名，該文本檔案包含已知的機器人且要從資料集中過濾掉的瀏覽器用戶代理清單。Adobe提供基線自動機查找檔案。 若未指定路徑，Data Workbench伺服器會在Data Workbench伺服器安裝目錄的「查閱」目錄中尋找此檔案。
   * **機器人查閱檔案，延伸：** 選用文字檔的路徑和檔案名稱，其中包含定義您的實作專用機器人的瀏覽器使用者代理或IP位址清單。此清單可包含內部監控機器人、測試指令碼，以及應從資料集中篩選掉之內部使用者的IP位址。 若未指定路徑，Data Workbench伺服器會在Data Workbench伺服器安裝目錄的「查閱」目錄中尋找此檔案。

   若記錄項目的瀏覽器使用者代理未列於任何查閱檔案中，則系統會將記錄項目視為由真實訪客產生，且不會從資料集中篩選。

   >[!NOTE]
   >
   >自動查閱檔案中的比對使用子字串來比較c-ip和cs(user-agent)記錄欄位。 如果搜索字串的開頭為「$」，則它必須匹配要測試的字串的前面，如果結尾為「$」，則搜索字串必須匹配要測試的字串的結尾。 如果搜索字串的開頭和結尾都是「$」，則字串必須與要篩選掉的日誌條目完全匹配。 例如，要測試C類塊中的所有IP地址，可以使用$231.78.123之類的字串在字串前面強制匹配。 這會符合地址231.78.123.0到231.78.123.255。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存檔案。

1. 若要讓本機所做的變更生效，請在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中檔案的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***，其中，設定檔名稱是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔。

   請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

   >[!NOTE]
   >
   >如果用於構建資料集的基礎日誌條目不發生更改（即使用於構建和更新資料集的轉換及其維度發生更改）至關重要，則應控制「自動查找檔案」、「基線」和「自動查找檔案」(Extended)的版本。 在這些檔案上放置版本號可確保對預設自動查找檔案的更新不會通過在這些檔案中添加或刪除條目而無意中更改先前構建的報表資料集。
