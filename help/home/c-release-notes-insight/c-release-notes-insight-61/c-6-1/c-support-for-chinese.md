---
description: Data Workbench用戶端應用程式現在支援簡體中文。
title: 簡體中文本地化
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 1%

---


# 簡體中文本地化{#simplified-chinese-localization}

Data Workbench用戶端應用程式現在支援簡體中文。

**安裝簡體中文**:

配置[!DNL Insight.exe]和支援檔案之前，必須退出客戶端應用程式。

1. 建立快捷方式，該快捷方式將命令行設定傳遞至[!DNL insight.exe]檔案。

   ```
   Insight.exe -zh-cn
   ```

1. 配置[!DNL Insight.cfg]以支援單位元組和雙位元組字型字元。

   Data Workbench目前支援英文和簡體中文。 您可以選取字型以支援以下兩種語言：

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. 重新啟動 [!DNL Insight.exe].

