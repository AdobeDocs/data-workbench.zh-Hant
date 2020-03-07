---
description: 'null'
solution: Insight,Analytics
title: 修改ExpPartialMatch參數（可選）
topic: Data workbench
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 修改ExpPartialMatch參數（可選）{#modifying-the-exppartialmatch-parameter-optional}

如果要啟用受控實驗將整個網站或網站的整個子目錄重新映射到另一個位置，可以將檔案中的ExpPartialMatch參數 [!DNL txlogd.conf] 設定為「on」。預設值為「off」。

以下是ExpPartialMatch參數的範例：

[!DNL ExpPartialMatch off]

將此參數設為「on」時請務必小心，因為這可能會導致您的整個網站在無意中重新對應。
