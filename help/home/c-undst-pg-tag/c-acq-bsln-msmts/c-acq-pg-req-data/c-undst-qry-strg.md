---
description: 由於HTTP的無狀態性，網站應用程式和網站開發人員通常會使用查詢字串(cs-uri-query)來傳遞頁面間的資訊。
title: 瞭解查詢字串
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# 瞭解查詢字串{#understanding-the-query-string}

{{eol}}

由於HTTP的無狀態性，網站應用程式和網站開發人員通常會使用查詢字串(cs-uri-query)來傳遞頁面間的資訊。

在許多情況下，當資訊被 [!DNL Sensor] 在web伺服器上。 此類資訊可由 [!DNL Site] 以說明網站的真正結構、訪客的路徑，以及其他資訊。

在某些動態網站中，查詢字串中的名稱=值配對（變數）對於判斷訪客所請求的實際頁面非常重要。 在這種情況下，URL可以以下列或類似的方式結構：

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

在此範例中，PAGENAME實際上是將提供給此URL之要求者之頁面的指標。 許多網站記錄檔分析工具和服務會限制網站運算子根據網站URL的查詢字串中發生的查詢字串變數，定義其網站中頁面的能力。 Data Workbench伺服器與Data Workbench可設定為使用此類查詢名稱來定義唯一頁面。 這很重要，因為許多系統會將下列URL解譯為相同頁面，但 [!DNL Site] 不會。

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
https://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

同樣地，網站開發人員和應用程式通常會在網站的URL中新增許多查詢字串變數，這些變數與識別要求的實際頁面無關。 範例如下所示：

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

在此範例中，查詢字串變數CAMPAIGN=已新增至URL。 此促銷活動變數用來指出哪個促銷活動導致訪客選取此URL。 [!DNL Site] 可設定為使用此CAMPAIGN資訊，但可將其與訪客檢視之頁面的定義分開，這樣您就能在頁面清單中看到下列內容，以便用於報告和分析用途：

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
