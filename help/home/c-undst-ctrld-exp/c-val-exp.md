---
description: 在您部署實驗後，您應驗證實驗是否正常運作。
solution: Insight,Analytics
title: 驗證實驗
topic: Data workbench
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 驗證實驗{#validating-the-experiment}

在您部署實驗後，您應驗證實驗是否正常運作。

如修改ExpCookieURL參 [數（可選）](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)，設定檔案中ExpCookieURL參數中指定的頁面可 [!DNL Sensor] 用來將自己放入特定實驗群組。

預設虛擬頁面 [!DNL /setcookie.htm]為，但您必須使用您在ExpCookieURL參數中設定的值。

## 請求測試頁面 {#section-8aed3b48d47f4e6c8869c0216f8781b1}

若要測試您網站的特定實驗群組，您的瀏覽器必須設定為接受Cookie，且您必須尚未擁有此網站的Cookie。

每次您要測試新群組時，請務必清除網站的Cookie。

若要將自己放入特定實驗的特定群組，請以下列格式以查詢字串來要求測試頁面：

[!DNL http://] *&lt;[!DNL sitename/?Experiment Name=Group Name]>*

例如：

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

當虛擬URL要求傳送至伺服器時， [!DNL Sensor] 會將您識別為指定實驗中指定群組的成員，然後將您重新導向至網站的根目錄。 您現在可以導覽至網站上的適當位置，以驗證是否顯示該實驗和群組的正確內容。

如果您要在瀏覽器中鍵入以下內容，瀏覽器會顯示網站的首頁，並將您放入New_Homepage實驗中的index2群組：

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

當index2群組中的訪客要求首頁時，頁面上會顯示較高的「要求展示」圖形連結，如下圖所示：

![](assets/TestPage.png)

