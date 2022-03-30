---
description: ExpCookieURL參數可用於test受控實驗工作正常。
solution: Analytics
title: 修改 ExpCookieURL 參數 (選用)
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# 修改 ExpCookieURL 參數 (選用){#modifying-the-expcookieurl-paramter-optional}

ExpCookieURL參數可用於test受控實驗工作正常。

此參數定義虛擬頁的URL，當請求時，虛擬頁會將您放入指定的實驗和組中，然後將您重定向到網站的根目錄。 從那個點到實驗結束，您是指定實驗和組的一部分。

此參數的預設頁是 [!DNL setcookie.htm]，但可以使用任何有效的虛擬URL。

>[!NOTE]
>
>這必須是虛擬URL，並且不能是真實頁面或現有內容的一部分。 Web伺服器上的指定路徑上不應有具有指定名稱的檔案。

以下是ExpCookieURL參數的示例：

[!DNL ExpCookieURL /setcookie.htm]
