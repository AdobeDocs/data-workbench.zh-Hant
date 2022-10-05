---
description: 關於如何根據數個案例在Transform.cfg檔案中指定參數的資訊。
title: Data Workbench Transform.cfg 檔案範例
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
exl-id: f7aadde4-6d89-4bd4-b34b-192a81a71dc3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Data Workbench Transform.cfg 檔案範例{#sample-data-workbench-transform-cfg-files}

{{eol}}

關於如何根據數個案例在Transform.cfg檔案中指定參數的資訊。

* [Simple Insight Transform.cfg檔案](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [使用逗號分隔值的輸出](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [取樣的記錄檔](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [依網站區段分割記錄檔](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

在每個範例中，檔案會顯示為 [!DNL Transform.cfg] data workbench中的視窗。

## 簡單Data WorkbenchTransform.cfg檔案 {#section-b7e83cafa3a947c597bd09d316930190}

以下 [!DNL Transform.cfg] 窗口提供讀取的說明 [!DNL .vsl] 檔案 [!DNL Logs] 目錄，並將x-timestring和x-trackingid欄位導出到儲存在Logs\VT目錄中的文本檔案。 由於未指定檔案旋轉週期或輸出檔案名格式，因此每個檔案都包含一個日曆日的資料，並且具有預設格式的名稱 [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SimpleExample.png)

## 使用逗號分隔值的輸出 {#section-03916934ad574efc8695abbae54a1816}

以下 [!DNL Transform.cfg] 窗口提供讀取的說明 [!DNL .vsl] 檔案從「記錄檔」目錄，並將欄位0至13匯出至逗號分隔( [!DNL .csv])檔案。 由於未指定檔案旋轉期間，每個檔案都包含一個日曆日的資料。 輸出檔案為 [!DNL .csv] 以格式命名的檔案 [!DNL %yyyy%%mm%%dd%-%x-mask%.csv].

![](assets/cfg_VisualTransform_CSVExample.png)

## 記錄檔範例 {#section-113b3b0c0c7547ea9536bb2f465c0875}

您可以配置轉換功能，以建立和維護完整日誌檔案的最新、精簡版本。 如此一來，您就能快速測試資料集設定，重新處理整個資料集的時間需為秒或分鐘，而非需要數小時。 以下範例提供如何設定轉換功能以執行此動作的範例。

以下 [!DNL Transform.cfg] 窗口提供讀取的說明 [!DNL .vsl] 檔案，並將x-timestring和x-trackingid欄位導出到儲存在Logs\VT目錄中的文本檔案。 指定的雜湊臨界值會篩選資料集中的特定追蹤ID，進而建立以100倍的因數取樣的資料集。 由於未指定檔案旋轉期間，每個檔案都包含一個日曆日的資料。 輸出檔案的名稱為預設格式 [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SampledExample.png)

## 依網站區段分割記錄檔 {#section-2cac205cd3934d31abb6c6ed8780196d}

以下 [!DNL Transform.cfg] 窗口提供讀取的說明 [!DNL .vsl]檔案，並將x-timestring和x-trackingid欄位導出到儲存在Logs\VT目錄中的文本檔案。 規則運算式轉換( [!DNL RETransform])作為輸入，會取用cs-uri-stem欄位並建立新欄位(x-site)來定義網站的區段。 x-site欄位包含在輸出文本檔案的名稱中，每個文本檔案都包含一個日曆日的資料。

![](assets/cfg_VisualTransform_SplittingExample.png)
