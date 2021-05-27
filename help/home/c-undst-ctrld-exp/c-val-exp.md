---
description: 部署實驗後，應驗證實驗是否正常運作。
solution: Analytics,Analytics
title: 驗證實驗
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# 驗證實驗{#validating-the-experiment}

部署實驗後，應驗證實驗是否正常運作。

如[修改ExpCookieURL參數（選用）](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)中所述，在[!DNL Sensor]設定檔案的ExpCookieURL參數中指定的頁面，可用來將自己放在特定實驗群組中。

預設虛擬頁面為[!DNL /setcookie.htm]，但您必須使用您在ExpCookieURL參數中設定的值。

## 請求測試頁面{#section-8aed3b48d47f4e6c8869c0216f8781b1}

若要測試網站的特定實驗群組，您的瀏覽器必須設定為接受Cookie，且您必須尚未擁有此網站的Cookie。

每次要測試新群組時，請務必清除網站的Cookie。

若要將自己放入特定實驗中的特定群組，請以下格式以查詢字串要求測試頁面：

[!DNL http://] *&lt;>>*[!DNL sitename/?Experiment Name=Group Name]

例如：

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

當虛擬URL要求傳送至伺服器時， [!DNL Sensor]會在指定實驗中將您識別為指定群組的成員，然後將您重新導向至網站的根目錄。 您現在可以導覽至網站上的適當位置，以驗證該實驗和群組是否顯示正確的內容。

如果要在瀏覽器中鍵入以下內容，則瀏覽器將顯示該網站的首頁，並將您放入New_Homepage實驗的index2組中：

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

當index2組中的訪客請求首頁時，「請求示範」圖形連結在頁面的上方顯示，如下圖所示：

![](assets/TestPage.png)
