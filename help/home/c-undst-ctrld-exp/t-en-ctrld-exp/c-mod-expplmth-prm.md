---
description: 修改 ExpPartialMatch 參數 (選用)
title: 修改 ExpPartialMatch 參數 (選用)
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# 修改 ExpPartialMatch 參數 (選用){#modifying-the-exppartialmatch-parameter-optional}

如果要啟用受控實驗將整個網站或網站的整個子目錄重新映射到另一個位置，可以將[!DNL txlogd.conf]檔案中的ExpPartialMatch參數設定為「on」。 預設值為「off」。

以下是ExpPartialMatch參數的範例：

[!DNL ExpPartialMatch off]

將此參數設為「on」時請務必小心，因為這可能會導致您的整個網站在無意中重新對應。
