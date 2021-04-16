---
description: 在「記錄處理資料集」中定義的網頁特定設定資訊，包括隨網站Adobe設定檔傳送的檔案。
title: 記錄處理的 Web 專屬設定
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
exl-id: abb6e6a7-011f-40d6-b778-16da2332af72
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# 記錄處理的 Web 專屬設定{#web-specific-settings-for-log-processing}

在「記錄處理資料集」中定義的網頁特定設定資訊，包括隨網站Adobe設定檔傳送的檔案。

由這些設定定義的過濾發生在日誌條目離開解碼器之後，且變換被應用，但在[!DNL Log Entry Condition]評估之前。

* [HTTP狀態篩選](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [機器人過濾](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## HTTP狀態篩選{#section-ac66acdcb6aa467d81c3721199e540fd}

您可以設定[!DNL Site]的實作，從資料集中移除sc-status代碼為400或更高的記錄項目。 成功的請求的狀態代碼小於400。 您的預設實作包含已設定HTTP狀態篩選的[!DNL Log Processing Dataset Include]檔案。

**要編輯HTTP狀態過濾的配置設定**

1. 在資料集描述檔中開啟[!DNL Profile Manager]，並開啟[!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg]檔案。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]的實作，則這些組態設定所在的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯檔案參數的值。 以下範例為指南。

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   有關[!DNL Range]條件的資訊，請參見[條件](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]** ，保存[!DNL HTTP Status Filter.cfg]檔案。

1. 要使本地更改生效，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>* ，其中配置檔案名稱是資料集配置檔案的名稱或資料集包含檔案所屬的繼承配置檔案。

   >[!NOTE]
   >
   >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。

## 機器人過濾{#section-7f43681dfbc64b969619cb88f97d5ad5}

您可以設定[!DNL Site]的實作，使用查閱檔案，從資料集移除由已知自動機產生的記錄項目、測試指令碼和內部使用者的IP位址。 您的預設實作包含已設定自動機篩選的[!DNL Log Processing Dataset Include]檔案。

**要編輯用於自動機過濾的配置設定，請執行以下操作：**

1. 在資料集描述檔中開啟[!DNL Profile Manager]，並開啟[!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg]檔案。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]的實作，則這些組態設定所在的檔案可能與描述的位置不同。

1. 使用下列範例和資訊作為參考線，檢視或編輯檔案的參數：

   ![](assets/cfg_WebParameters_RobotFilter.png)

   該檔案包含由以下三個參數定義的[!DNL NotRobotCondition]:

   * **不區分大小寫的自動機過濾：** True或false。如果為true，在自動機過濾中不會考慮字母大小寫（上／下）。
   * **自動機查找檔案，基** 線：文本檔案的路徑和檔案名，該文本檔案包含已知自動機且要從資料集中過濾的瀏覽器用戶代理的清單。Adobe提供基線自動機查找檔案。 如果您未指定路徑，資料工作台伺服器會在資料工作台伺服器安裝目錄的「查閱」目錄中尋找此檔案。
   * **自動機查閱檔案，擴** 充：可選文字檔案的路徑和檔案名稱，其中包含瀏覽器使用者代理或IP位址清單，可定義您實作專用的自動機。此清單可包含內部監控自動機、測試指令碼，以及應從資料集中篩選的內部使用者的IP位址。 如果您未指定路徑，資料工作台伺服器會在資料工作台伺服器安裝目錄的「查閱」目錄中尋找此檔案。

   如果某個記錄項目的瀏覽器使用者代理未列在任一查閱檔案中，則該記錄項目會被視為由實際訪客產生，且不會從資料集中篩選。

   >[!NOTE]
   >
   >自動機查閱檔案中的比對使用子字串來比較c-ip和cs(user-agent)記錄檔欄位。 如果搜尋字串以&quot;$&quot;開頭，則必須符合正在測試的字串前方，如果結尾為&quot;$&quot;，則搜尋字串必須符合正在測試的字串結尾。 如果搜尋字串皆以&quot;$&quot;開頭和結尾，則字串必須完全符合，才能篩選出記錄項目。 例如，要測試C類塊中的所有IP地址，您應使用一個字串，如$231.78.123。在字串前面強制匹配。 這會比對地址231.78.123.0到231.78.123.255。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存檔案。

1. 要使本地更改生效，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>* ，其中配置檔案名稱是資料集配置檔案的名稱或資料集包含檔案所屬的繼承配置檔案。

   請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。

   >[!NOTE]
   >
   >如果用於構建資料集的基礎日誌條目沒有更改（即使用於構建和更新資料集的轉換及其尺寸有所更改），則應控製版本。 在這些檔案上放置版本號碼可確保對預設自動機查閱檔案的更新不會透過新增或刪除這些檔案中的項目，無意中變更先前建立的報表資料集。
