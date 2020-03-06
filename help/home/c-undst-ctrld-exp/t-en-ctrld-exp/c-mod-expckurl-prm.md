---
description: ExpCookieURL參數可用來測試您的受控實驗是否正常運作。
solution: Insight,Analytics
title: 修改ExpCookieURL參數（可選）
topic: Data workbench
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 修改ExpCookieURL參數（可選）{#modifying-the-expcookieurl-paramter-optional}

ExpCookieURL參數可用來測試您的受控實驗是否正常運作。

此參數會定義虛擬頁面的URL，當要求時將您放入指定的實驗和群組，然後將您重新導向至網站的根目錄。 從那個點到實驗結束，您都是指定實驗和群組的一部分。

此參數的預設頁面為 [!DNL setcookie.htm]，但您可以使用任何有效的虛擬URL。

>[!NOTE]
>
>這必須是虛擬URL，且不得是實際頁面或現有內容的一部分。 在指定的路徑上，Web伺服器上不應存在具有指定名稱的檔案。

以下是ExpCookieURL參數的範例：

[!DNL ExpCookieURL /setcookie.htm]
