---
description: 資料工作台用戶端應用程式現在支援簡體中文。
solution: Analytics
title: 簡體中文本地化
topic: Data workbench
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 簡體中文本地化{#simplified-chinese-localization}

資料工作台用戶端應用程式現在支援簡體中文。

**安裝簡體中文**:

在配置和 [!DNL Insight.exe] 支援檔案之前，您必須退出客戶端應用程式。

1. 建立在命令行設定中傳遞給檔案的快捷 [!DNL insight.exe] 方式。

   ```
   Insight.exe -zh-cn
   ```

1. 設定 [!DNL Insight.cfg] 為支援單位元組和雙位元組字型字元。

   資料工作台目前支援英文和簡體中文。 您可以選取字型以支援這兩種語言：

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. 重新啟動 [!DNL Insight.exe].

