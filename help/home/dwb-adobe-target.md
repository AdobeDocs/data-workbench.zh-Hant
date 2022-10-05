---
description: 將Data Workbench與Adobe Target整合。 匯出資料區段並自動填入匯出檔案。
title: Data Workbench 與 Adobe Target 整合
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Data Workbench 與 Adobe Target 整合

{{eol}}

將AdobeData Workbench與Adobe Target整合更輕鬆，提供Data Workbench功能來匯出資料區段並自動填入匯出檔案。

AdobeData Workbench提供與Adobe Target的封閉回圈整合，以共用資料和產生報表。 在Data Workbench內，您可以使用所有可用資料分析有意義區段的母體，包括透過通路（例如電話、商店等）進行離線轉換。

例如，某位訪客在您的網站上尋找鞋子，但未轉換。 相反地，訪客下載的抵用券是下次購買優惠20%，然後在您的商店購買襯衫。 您可以使用Data Workbench來收集該資料，然後將該設定檔資料推回Target，以顯示訪客已離線購買襯衫。 然後，您可以在通常Target可能會嘗試將鞋類重新行銷給該訪客時，將領帶商品的促銷活動定位給該訪客。

## 使用Adobe Target設定Data Workbench

1. 以滑鼠右鍵按一下 [!UICONTROL Detail Table] 窗口。

   ![](assets/insight-to-tnt.png)

1. 選擇 **[!UICONTROL New Target Export]** 並在 **[!UICONTROL Save As]** 命令。

1. 按一下 **[!UICONTROL Save Export File]**。

   將會開啟匯出範本視窗。

   所有Adobe Target資訊皆會自動填入。 它會根據您在區段匯出中所放置的內容建立參數清單。 完成後，Data Workbench會將資料傳送至Adobe Target伺服器。

   **注意：** 範本檔案應由 [!UICONTROL Profile Architect]. 此 [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host]，和 [!UICONTROL Mbox Name] 需要輸入。 如果您有多個網站，請填寫多個範本並儲存至伺服器。 設定檔管理員的範本位於 `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. 指定 [!UICONTROL mboxPC] 查詢參數。

   如果Data Workbench屬性的名稱不是 [!UICONTROL mboxPC]，您必須編輯適當的「查詢參數」，並將其重新命名為 _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   將導出檔案保存到伺服器後，導出將開始。 完成後， [!UICONTROL TnTSend.exe] 應用程式會啟動，並開始傳送資料至Target帳戶。

## 設定Target的Data Workbench

在Adobe Target中完成下列工作：

Data Workbench正在將使用者設定檔傳遞至Adobe Target。 若要設定匯出至Target，您必須設定並啟用其API，並提供 **[!UICONTROL clientname]** 和 **[!UICONTROL domain postfix]** 導出配置檔案的參數(`export.cfg`)。

名為的新布林值選項 **[!UICONTROL Oneshot]** 已新增至區段匯出檔案。 此選項包含在隨新設定檔分發的範本檔案中。 若 [!UICONTROL Oneshot] 設為 _true_，則 `.export` 檔案將重新命名為 `.export.done-TIMESTAMP` 匯出完成後，請確保區段永遠不會匯出多次。 這在匯出至Adobe Target時很重要。

**注意：** 從Data Workbench到Adobe Target的呼叫會計為 [!UICONTROL mbox] 呼叫，每個已傳送的設定檔都需要一個呼叫。 因此，如果兩個解決方案之間需要多次呼叫，成本就會增加。

不完整的配置會在日誌中生成以下錯誤消息：

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## 設定Adobe Target以Data Workbench

在Adobe Target中，客戶無需特殊設定即可傳送設定檔資料。 使用者的設定檔資訊通常會以 [!UICONTROL mbox] 請求，且伺服器會將設定檔參數設為標準功能，以供目標促銷活動設定使用，而無需進行任何其他設定。

Adobe Target內建Data Workbench整合，可從「超級使用者用戶端詳細資料」頁面啟用。 啟用選項會顯示從Adobe Target內Data Workbench共用的區段，以便供鎖定目標使用。

## 在ExportIntegration.exe中設定HTTP日誌報告

將長報告減少到 [!UICONTROL HTTP.log] 使用 [!UICONTROL ExportIntegration.exe] 匯出Adobe Target整合檔案。

新 [!UICONTROL httpLoggingEI.cfg] 組態檔(位於 `server\Admin\Export\httpLoggingEI.cfg`)可讓您減少詳細記錄至 [!UICONTROL HTTP.log] 使用導出資料時的檔案 [!UICONTROL ExportIntegration.exe]. 這可讓您停止詳細請求/回應記錄。

已在中捕獲詳細日誌 [!UICONTROL TnTSend.log] 檔案。

_True_ 設定詳細日誌記錄，和 _False_ 停止詳細記錄 [!UICONTROL HTTP.log] 檔案。

在False設定中，只會傳送警告訊息至 [!UICONTROL HTTP.log] 檔案（未傳送資訊內容）。
