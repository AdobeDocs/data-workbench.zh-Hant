---
description: 修改 ExpPartialMatch 參數 (選用)
title: 修改 ExpPartialMatch 參數 (選用)
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# 修改 ExpPartialMatch 參數 (選用){#modifying-the-exppartialmatch-parameter-optional}

{{eol}}

如果您想要啟用受控實驗，將您的整個網站或網站的整個子目錄重新對應至其他位置，您可以在 [!DNL txlogd.conf] 檔案設為「開啟」。 預設值為「off」。

以下是ExpPartialMatch參數的範例：

[!DNL ExpPartialMatch off]

將此參數設為「on」時請務必小心，因為這可能導致無意中重新對應整個網站。
