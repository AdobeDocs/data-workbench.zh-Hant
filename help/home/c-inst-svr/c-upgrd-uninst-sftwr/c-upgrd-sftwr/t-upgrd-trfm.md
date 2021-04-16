---
description: 升級轉換資料夾的步驟。
title: 升級轉換
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# 升級轉換{#upgrading-transform}

升級轉換資料夾的步驟。

1. 開啟[!DNL Insight Server]發行套件的[!DNL .zip]檔案，並開啟該[!DNL .zip]檔案中的[!DNL Profiles]檔案夾。
1. 將[!DNL Transform]資料夾複製到[!DNL Insight Server]安裝目錄的[!DNL Profiles]資料夾。 這樣做會覆寫現有的[!DNL Transform]資料夾。
1. 對於繼承[!DNL Transform]配置檔案的每個配置檔案，請確認[!DNL profile.cfg]檔案在目錄向量中有一個「轉換」條目。
資料重新處理在設定檔同步後開始。
