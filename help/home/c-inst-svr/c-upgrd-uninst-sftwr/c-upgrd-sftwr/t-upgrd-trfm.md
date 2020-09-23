---
description: 升級轉換資料夾的步驟。
solution: Analytics
title: 升級轉換
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---


# 升級轉換{#upgrading-transform}

升級轉換資料夾的步驟。

1. 開啟 [!DNL .zip] 發行套件 [!DNL Insight Server] 的檔案，並開啟該 [!DNL Profiles] 檔案中的資 [!DNL .zip] 料夾。
1. 將檔案 [!DNL Transform] 夾複製到安 [!DNL Profiles] 裝目錄中 [!DNL Insight Server] 的資料夾。 執行此動作會覆寫現有的資 [!DNL Transform] 料夾。
1. 對於繼承配置檔案的 [!DNL Transform] 每個配置檔案，請確 [!DNL profile.cfg] 認檔案在「目錄」向量中有「轉換」條目。
資料重新處理在設定檔同步後開始。
