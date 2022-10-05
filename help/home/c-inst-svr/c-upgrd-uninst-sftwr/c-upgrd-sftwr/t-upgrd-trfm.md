---
description: 升級轉換資料夾的步驟。
title: 升級轉換
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# 升級轉換{#upgrading-transform}

{{eol}}

升級轉換資料夾的步驟。

1. 開啟 [!DNL .zip] 檔案 [!DNL Insight Server] 發行套件，然後開啟 [!DNL Profiles] 資料夾 [!DNL .zip] 檔案。
1. 複製 [!DNL Transform] 檔案夾 [!DNL Profiles] 檔案夾 [!DNL Insight Server] 安裝目錄。 這麼做會覆寫現有 [!DNL Transform] 檔案夾。
1. 對於繼承 [!DNL Transform] 設定檔，確認 [!DNL profile.cfg] 檔案的「目錄」向量中有「轉換」條目。
資料重新處理在同步設定檔後開始。
