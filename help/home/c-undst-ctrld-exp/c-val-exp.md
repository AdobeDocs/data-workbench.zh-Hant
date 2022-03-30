---
description: 部署了實驗後，應驗證實驗是否正常工作。
solution: Analytics
title: 驗證實驗
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# 驗證實驗{#validating-the-experiment}

部署了實驗後，應驗證實驗是否正常工作。

如中所述 [修改ExpCookieURL參數（可選）](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)，在中的ExpCookieURL參數中指定的頁 [!DNL Sensor] 配置檔案可用於將自己放入特定的實驗組。

預設虛擬頁是 [!DNL /setcookie.htm]，但必須使用在ExpCookieURL參數中設定的值。

## 請求Test頁 {#section-8aed3b48d47f4e6c8869c0216f8781b1}

要test網站的特定實驗組，必須將瀏覽器配置為接受cookie，並且您不得已擁有此網站的cookie。

每次要test新組時，請確保清除網站的Cookie。

要將您自己放入特定實驗中的特定組，請以以下格式請求具有查詢字串的test頁：

[!DNL https://] *&lt; [!DNL sitename/?Experiment Name=Group Name]>*

例如：

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

當虛擬URL請求發送到伺服器時， [!DNL Sensor] 將您標識為指定實驗中指定組的成員，然後將您重定向到網站的根目錄。 現在，您可以導航到網站上的適當位置，以驗證是否顯示了該實驗和組的正確內容。

如果要在瀏覽器中鍵入以下內容，瀏覽器將顯示網站的首頁，並將您放入New_Homepage實驗中的index2組：

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

當index2組中的訪問者請求首頁時，「請求演示」圖形連結將在頁面上顯示得更高，如下圖所示：

![](assets/TestPage.png)
