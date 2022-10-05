---
description: ExpCookieURL參數可用來測試受控實驗是否正常運作。
solution: Analytics
title: 修改 ExpCookieURL 參數 (選用)
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# 修改 ExpCookieURL 參數 (選用){#modifying-the-expcookieurl-paramter-optional}

{{eol}}

ExpCookieURL參數可用來測試受控實驗是否正常運作。

此參數會定義虛擬頁面的URL，當請求時，該URL會將您放入指定的實驗和群組，然後將您重新導向至網站的根目錄。 從該點到實驗結尾，您是指定實驗和組的一部分。

此參數的預設頁面為 [!DNL setcookie.htm]，但您可以使用任何有效的虛擬URL。

>[!NOTE]
>
>這必須是虛擬URL，且不得是真實頁面或現有內容的片段。 Web伺服器上的指定路徑上不應存在具有指定名稱的檔案。

以下是ExpCookieURL參數的範例：

[!DNL ExpCookieURL /setcookie.htm]
