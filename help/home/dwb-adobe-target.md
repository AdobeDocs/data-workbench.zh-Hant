---
description: 將Data Workbench與Adobe Target整合。 匯出資料區段並自動填入匯出檔案。
title: Data Workbench 與 Adobe Target 整合
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Data Workbench 與 Adobe Target 整合

將AdobeData Workbench與Adobe Target整合起來變得更容易，因為Data Workbench功能可匯出資料區段並自動填入匯出檔案。

AdobeData Workbench提供與Adobe Target的閉環整合，以分享資料並產生報告。 在Data Workbench中，您可以使用所有可用資料來分析有意義的群體人口族群，包括透過通道（例如電話、商店等）進行離線轉換。

例如，訪客在您的網站上尋找鞋，但未轉換。 相反地，訪客下載的抵用券是下次購買的20%，然後在您的商店購買襯衫。 使用Data Workbench，您可以收集該資料，然後將該描述檔資料推回Target，以顯示訪客離線購買了一件襯衫。 然後，當Target嘗試將鞋類商品重新行銷給該訪客時，您就可以定位領帶選件的促銷活動。

## 與Adobe Target建立Data Workbench

1. 在[!UICONTROL Detail Table]窗口中按一下右鍵標題。

   ![](assets/insight-to-tnt.png)

1. 選擇&#x200B;**[!UICONTROL New Target Export]** ，然後在菜單的&#x200B;**[!UICONTROL Save As]**&#x200B;命令下輸入新導出檔案的名稱。

1. 按一下 **[!UICONTROL Save Export File]**。

   將會開啟匯出範本視窗。

   所有Adobe Target資訊都會自動填入。 它會根據您在區段匯出中所放置的內容建立參數清單。 完成後，Data Workbench將將資料發送到Adobe Target伺服器。

   **注意：** 範本檔案應由設定 [!UICONTROL Profile Architect]。需要輸入[!UICONTROL Client Name]、[!UICONTROL Domain Postfix]、[!UICONTROL Mbox Host]和[!UICONTROL Mbox Name]。 如果您有多個網站，請填寫多個範本並儲存至伺服器。 「配置式管理器」中的模板位於`Context\FileNew\Detail Table\Export\Copy`中。

   ![](assets/insight-to-tnt1.png)

1. 指定[!UICONTROL mboxPC]查詢參數。

   如果Data Workbench屬性的名稱不是[!UICONTROL mboxPC]，則必須編輯適當的查詢參數，並將其更名為&#x200B;_mboxPC_。

   ![](assets/insight-to-tnt2.png)

   將導出檔案保存到伺服器後，將開始導出。 完成後，[!UICONTROL TnTSend.exe]應用程式將啟動並開始傳送資料至Target帳戶。

## 配置目標Data Workbench

在Adobe Target完成下列工作：

Data Workbench正在將用戶配置檔案傳遞到Adobe Target。 若要設定匯出至Target，您必須設定並啟用其API，並提供匯出設定檔案的&#x200B;**[!UICONTROL clientname]**&#x200B;和&#x200B;**[!UICONTROL domain postfix]**&#x200B;參數(`export.cfg`)。

新的布爾選項&#x200B;**[!UICONTROL Oneshot]**&#x200B;已添加到段導出檔案。 此選項包含在隨新配置檔案分發的模板檔案中。 如果[!UICONTROL Oneshot]設為&#x200B;_true_，則在匯出完成後，`.export`檔案將重新命名為`.export.done-TIMESTAMP`，以確保區段不會多次匯出。 這在出口到Adobe Target時很重要。

**注意：從** Data Workbench到Adobe Target的呼叫會計為呼叫，每 [!UICONTROL mbox] 個傳送的描述檔需要一個呼叫。因此，如果兩個解決方案之間需要多次呼叫，成本就會增加。

配置不完整會在日誌中生成以下錯誤消息：

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## 將Adobe Target配置為Data Workbench

在Adobe Target，客戶無需特殊配置即可發送配置檔案資料。 一般會在一般的[!UICONTROL mbox]要求中傳遞使用者的描述檔資訊，而伺服器會將描述檔參數設為標準功能，以供定位促銷活動設定使用，而不需進行任何額外的設定。

Adobe Target已內建Data Workbench整合，可從「超級用戶客戶端詳細資訊」頁啟用。 啟用此選項將會呈現從Adobe TargetData Workbench共用的區段，以便用於定位。

## 在ExportIntegration.exe中設定HTTP記錄檔報告

使用[!UICONTROL ExportIntegration.exe]匯出Adobe Target整合檔案時，將長報告縮短至[!UICONTROL HTTP.log]。

新的[!UICONTROL httpLoggingEI.cfg]配置檔案（位於`server\Admin\Export\httpLoggingEI.cfg`）可讓您減少在使用[!UICONTROL ExportIntegration.exe]導出資料時對[!UICONTROL HTTP.log]檔案進行詳細記錄。 這可讓您停止詳細請求／回應記錄。

已在[!UICONTROL TnTSend.log]檔案中捕獲詳細記錄。

_Truesets verbose logging_ 和 __ Falses stops verbose logging to  [!UICONTROL HTTP.log] file.

在False設定中，只有警告訊息會傳送至[!UICONTROL HTTP.log]檔案（未傳送資訊內容）。
