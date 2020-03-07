---
description: 由於HTTP的無狀態性質，網站應用程式和網站開發人員通常會使用查詢字串(cs-uri-query)來將資訊從頁面傳遞至頁面。
solution: Analytics
title: 瞭解查詢字串
topic: Data workbench
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 瞭解查詢字串{#understanding-the-query-string}

由於HTTP的無狀態性質，網站應用程式和網站開發人員通常會使用查詢字串(cs-uri-query)來將資訊從頁面傳遞至頁面。

在許多情況下，當查詢字串在Web伺服器上取得時，資訊可 [!DNL Sensor] 以傳入。 此類資訊可用來 [!DNL Site] 說明網站的真實結構、訪客的路徑，以及其他資訊。

在某些動態網站中，查詢字串中的name=value配對（變數）對於判斷訪客要求的實際頁面很重要。 在這種情況下，URL的結構可能是：

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

在此範例中，PAGENAME實際上是指示該URL的請求者將提供哪個頁面。 許多網站記錄檔分析工具和服務會限制網站營運商根據網站URL的查詢字串中出現的查詢字串變數，定義其網站中頁面的能力。 資料工作台伺服器和資料工作台可以配置為使用這樣的查詢名稱來定義唯一頁面。 這很重要，因為許多系統會將下列URL解譯為相同的頁面，但 [!DNL Site] 不會。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

同樣地，網站開發人員和應用程式通常會在網站的URL中新增許多查詢字串變數，這些變數與識別所請求的實際頁面無關。 範例如下：

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

在此範例中，查詢字串變數CAMPAIGN=已新增至URL。 此CAMPAIGN變數可用來指出哪個行銷促銷活動導致訪客選取此URL。 [!DNL Site] 可設定為使用此CAMPAIGN資訊，但將其與訪客檢視之頁面的定義分開，如此，在您的頁面清單中，您只會看到下列內容：

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
