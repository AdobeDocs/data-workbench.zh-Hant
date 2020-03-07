---
description: 將資料工作台與Adobe Target整合。 匯出資料區段並自動填入匯出檔案。
solution: Analytics
title: 資料工作台與Adobe Target整合
topic: Data workbench
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 資料工作台與Adobe Target整合

Adobe Data Workbench與Adobe Target的整合更輕鬆，因為Data Workbench功能可讓您匯出資料區段並自動填入匯出檔案。

Adobe資料工作台提供與Adobe Target的閉環整合，以共用資料和產生報表。 在資料工作台中，您可以使用所有可用資料來分析有意義的群體人口族群，包括透過通道（例如電話、商店等）進行離線轉換。

例如，訪客在您的網站上尋找鞋，但未轉換。 相反地，訪客下載的抵用券是下次購買的20%，然後在您的商店購買襯衫。 使用「資料工作台」，您可以收集該資料，然後將該描述檔資料推回Target，以顯示訪客離線購買了一件襯衫。 然後，當Target嘗試將鞋類商品重新行銷給該訪客時，您就可以定位領帶選件的促銷活動。

## 使用Adobe Target設定資料工作台

1. 在視窗中按一下標題 [!UICONTROL Detail Table] 右鍵。

   ![](assets/insight-to-tnt.png)

1. 選 **[!UICONTROL New Target Export]** 擇並在菜單中的命令下輸入新導出 **[!UICONTROL Save As]** 檔案的名稱。

1. 按一下 **[!UICONTROL Save Export File]**.

   將會開啟匯出範本視窗。

   所有Adobe Target資訊都會自動填入。 它會根據您在區段匯出中所放置的內容建立參數清單。 資料工作台完成後，會將資料傳送至Adobe Target伺服器。

   **注意：** 範本檔案應由設定 [!UICONTROL Profile Architect]。 必 [!UICONTROL Client Name]須輸 [!UICONTROL Domain Postfix]入、 [!UICONTROL Mbox Host]和 [!UICONTROL Mbox Name] 等。 如果您有多個網站，請填寫多個範本並儲存至伺服器。 「配置檔案管理器」中的模板位於 `Context\FileNew\Detail Table\Export\Copy`中。

   ![](assets/insight-to-tnt1.png)

1. 指定查 [!UICONTROL mboxPC] 詢參數。

   如果「資料工作台」屬性的名稱不是其他值 [!UICONTROL mboxPC]，您必須編輯適當的「查詢參數」，並將其重新命名 _為mboxPC_。

   ![](assets/insight-to-tnt2.png)

   將導出檔案保存到伺服器後，將開始導出。 完成後，應用 [!UICONTROL TnTSend.exe] 程式會啟動並開始傳送資料至Target帳戶。

## 為Target設定資料工作台

在Adobe Target中完成下列工作：

資料工作台正在將使用者設定檔傳遞至Adobe Target。 若要設定匯出至Target，您必須設定並啟用其API，並提供匯 **[!UICONTROL clientname]** 出 **[!UICONTROL domain postfix]** 設定檔(`export.cfg`)的參數。

已將名為的新布林 **[!UICONTROL Oneshot]** 選項新增至區段匯出檔案。 此選項包含在隨新配置檔案分發的模板檔案中。 如果 [!UICONTROL Oneshot] 設為 _true_，則匯出完成後 `.export` ，檔案將重新命名為 `.export.done-TIMESTAMP` ，以確保區段不會多次匯出。 這在匯出至Adobe Target時很重要。

**注意：** 從資料工作台到Adobe Target的呼叫會計為呼叫，每 [!UICONTROL mbox] 個傳送的描述檔需要一次呼叫。 因此，如果兩個解決方案之間需要多次呼叫，成本就會增加。

配置不完整會在日誌中生成以下錯誤消息：

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## 設定Adobe Target的資料工作台

在Adobe Target中，客戶不需要特殊設定即可傳送個人檔案資料。 一般會在一般要求中傳遞使用者的描述檔資訊，而伺服器會將描述檔參數 [!UICONTROL mbox] 設為標準功能，以供定位促銷活動設定使用，而不需進行任何額外設定。

Adobe Target內建了資料工作台整合，可從「超級使用者用戶端詳細資訊」頁面啟用。 啟用此選項會呈現從Adobe Target內的「資料工作台」共用的區段，以便用於定位。

## 在ExportIntegration.exe中設定HTTP記錄檔報告

使用匯出Adobe Target整 [!UICONTROL HTTP.log] 合檔案 [!UICONTROL ExportIntegration.exe] 時，可縮短報告時間。

新的配 [!UICONTROL httpLoggingEI.cfg] 置檔案(位於 `server\Admin\Export\httpLoggingEI.cfg`)可讓您減少在使用導出資料時對 [!UICONTROL HTTP.log] 檔案進行詳細記錄的情況 [!UICONTROL ExportIntegration.exe]。 這可讓您停止詳細請求／回應記錄。

已在檔案中捕獲詳細 [!UICONTROL TnTSend.log] 記錄。

_True_ 會設定詳細記錄， _False會停止詳細記錄至_[!UICONTROL HTTP.log] 檔案。

在「錯誤」設定中，只有警告訊息會傳送至 [!UICONTROL HTTP.log] 檔案（未傳送資訊內容）。