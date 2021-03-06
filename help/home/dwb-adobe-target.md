---
description: 將Data Workbench與Adobe Target整合。 匯出資料區段並自動填入匯出檔案。
title: Data Workbench 與 Adobe Target 整合
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Data Workbench 與 Adobe Target 整合

將AdobeData Workbench與Adobe Target整合更輕鬆，提供Data Workbench功能來匯出資料區段並自動填入匯出檔案。

AdobeData Workbench提供與Adobe Target的封閉回圈整合，以共用資料和產生報表。 在Data Workbench內，您可以使用所有可用資料分析有意義區段的母體，包括透過通路（例如電話、商店等）進行離線轉換。

例如，某位訪客在您的網站上尋找鞋子，但未轉換。 相反地，訪客下載的抵用券是下次購買優惠20%，然後在您的商店購買襯衫。 您可以使用Data Workbench來收集該資料，然後將該設定檔資料推回Target，以顯示訪客已離線購買襯衫。 然後，您可以在通常Target可能會嘗試將鞋類重新行銷給該訪客時，將領帶商品的促銷活動定位給該訪客。

## 使用Adobe Target設定Data Workbench

1. 在[!UICONTROL Detail Table]視窗中按一下右鍵標題。

   ![](assets/insight-to-tnt.png)

1. 選擇&#x200B;**[!UICONTROL New Target Export]**&#x200B;並在菜單的&#x200B;**[!UICONTROL Save As]**&#x200B;命令下輸入新導出檔案的名稱。

1. 按一下 **[!UICONTROL Save Export File]**。

   將會開啟匯出範本視窗。

   所有Adobe Target資訊皆會自動填入。 它會根據您在區段匯出中所放置的內容建立參數清單。 完成後，Data Workbench會將資料傳送至Adobe Target伺服器。

   **注意：** 範本檔案應由 [!UICONTROL Profile Architect]設定。需要輸入[!UICONTROL Client Name]、[!UICONTROL Domain Postfix]、[!UICONTROL Mbox Host]和[!UICONTROL Mbox Name]。 如果您有多個網站，請填寫多個範本並儲存至伺服器。 配置檔案管理器中的模板位於`Context\FileNew\Detail Table\Export\Copy`中。

   ![](assets/insight-to-tnt1.png)

1. 指定[!UICONTROL mboxPC]查詢參數。

   如果Data Workbench屬性的名稱不是[!UICONTROL mboxPC]，則必須編輯適當的查詢參數，並將其重新命名為&#x200B;_mboxPC_。

   ![](assets/insight-to-tnt2.png)

   將導出檔案保存到伺服器後，導出將開始。 完成後，[!UICONTROL TnTSend.exe]應用程式將啟動並開始傳送資料至Target帳戶。

## 設定Target的Data Workbench

在Adobe Target中完成下列工作：

Data Workbench正在將使用者設定檔傳遞至Adobe Target。 若要設定匯出至Target，您必須設定並啟用其API，並提供匯出設定檔案(`export.cfg`)的&#x200B;**[!UICONTROL clientname]**&#x200B;和&#x200B;**[!UICONTROL domain postfix]**&#x200B;參數。

區段匯出檔案已新增名為&#x200B;**[!UICONTROL Oneshot]**&#x200B;的新布林值選項。 此選項包含在隨新設定檔分發的範本檔案中。 如果將[!UICONTROL Oneshot]設為&#x200B;_true_，則在匯出完成後，會將`.export`檔案重新命名為`.export.done-TIMESTAMP`，確保絕不會多次匯出區段。 這在匯出至Adobe Target時很重要。

**注意：** 從Data Workbench到Adobe Target的呼叫會計為呼叫， [!UICONTROL mbox] 每個傳送的設定檔都需要一個呼叫。因此，如果兩個解決方案之間需要多次呼叫，成本就會增加。

不完整的配置會在日誌中生成以下錯誤消息：

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## 設定Adobe Target以Data Workbench

在Adobe Target中，客戶無需特殊設定即可傳送設定檔資料。 一般會在一般的[!UICONTROL mbox]請求中傳遞使用者的設定檔資訊，而伺服器會將設定檔參數設為可用於目標促銷活動設定的標準功能，而不需進行任何其他設定。

Adobe Target內建Data Workbench整合，可從「超級使用者用戶端詳細資料」頁面啟用。 啟用選項會顯示從Adobe Target內Data Workbench共用的區段，以便供鎖定目標使用。

## 在ExportIntegration.exe中設定HTTP日誌報告

使用[!UICONTROL ExportIntegration.exe]匯出Adobe Target整合檔案時，減少報表長度至[!UICONTROL HTTP.log]。

新的[!UICONTROL httpLoggingEI.cfg]配置檔案（位於`server\Admin\Export\httpLoggingEI.cfg`）可讓您在使用[!UICONTROL ExportIntegration.exe]匯出資料時，減少對[!UICONTROL HTTP.log]檔案的詳細記錄。 這可讓您停止詳細請求/回應記錄。

已在[!UICONTROL TnTSend.log]檔案中捕獲詳細日誌。

__ Truesets詳細記錄，和 __ False停止詳細記錄至 [!UICONTROL HTTP.log] 檔案。

在False設定中，只會傳送警告訊息至[!UICONTROL HTTP.log]檔案（未傳送資訊內容）。
