---
description: 有關如何根據數個藍本，在Transform.cfg檔案中指定參數的資訊。
title: Data Workbench Transform.cfg 檔案範例
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
exl-id: f7aadde4-6d89-4bd4-b34b-192a81a71dc3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Data Workbench Transform.cfg 檔案範例{#sample-data-workbench-transform-cfg-files}

有關如何根據數個藍本，在Transform.cfg檔案中指定參數的資訊。

* [簡單的Insight Transform.cfg檔案](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [使用逗號分隔值輸出](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [取樣的記錄檔](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [依網站區段分割記錄檔](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

在每個範例中，檔案會顯示為資料工作台的[!DNL Transform.cfg]視窗。

## 簡單的Data Workbench轉換。cfg檔案{#section-b7e83cafa3a947c597bd09d316930190}

以下[!DNL Transform.cfg]窗口提供從[!DNL Logs]目錄讀取[!DNL .vsl]檔案並將x-timestring和x-trackingid欄位導出到儲存在Logs\VT目錄中的文本檔案的說明。 由於未指定檔案旋轉週期或輸出檔案名格式，因此每個檔案都包含一個日曆日的資料，並且其名稱為預設格式[!DNL %yyyy%%mm%%dd%-%x-mask%.txt]。

![](assets/cfg_VisualTransform_SimpleExample.png)

## 使用逗號分隔值{#section-03916934ad574efc8695abbae54a1816}的輸出

以下[!DNL Transform.cfg]窗口提供從Logs目錄讀取[!DNL .vsl]檔案並將欄位0到13導出到儲存在Logs\VT\CSV directory目錄中的逗號分隔([!DNL .csv])檔案的說明。 由於未指定檔案旋轉期間，因此每個檔案都包含一個日曆日的資料。 輸出檔案是以[!DNL %yyyy%%mm%%dd%-%x-mask%.csv]格式命名的[!DNL .csv]檔案。

![](assets/cfg_VisualTransform_CSVExample.png)

## 日誌檔案示例{#section-113b3b0c0c7547ea9536bb2f465c0875}

您可以配置轉換功能，以建立和維護完整日誌檔案的最新、精簡版。 如此可讓您快速測試資料集設定，重新處理時間為數秒或數分鐘，而非重新處理整個資料集所需的數小時。 下面的示例提供了如何配置轉換功能以執行此操作的示例。

以下[!DNL Transform.cfg]窗口提供了從Logs目錄讀取[!DNL .vsl]檔案並將x-timestring和x-trackingid欄位導出到Logs\VT目錄中儲存的文本檔案的說明。 指定的雜湊臨界值會從資料集中篩選特定追蹤ID，從而建立以100倍系數取樣的資料集。 由於未指定檔案旋轉期間，因此每個檔案都包含一個日曆日的資料。 輸出檔案的名稱為預設格式[!DNL %yyyy%%mm%%dd%-%x-mask%.txt]。

![](assets/cfg_VisualTransform_SampledExample.png)

## 依網站區段分割記錄檔{#section-2cac205cd3934d31abb6c6ed8780196d}

以下[!DNL Transform.cfg]窗口提供了從Logs目錄讀取[!DNL .vsl]檔案並將x-timestring和x-trackingid欄位導出到Logs\VT目錄中儲存的文本檔案的說明。 規則運算式轉換([!DNL RETransform])會將cs-uri-stem欄位作為輸入，並建立新欄位(x-site)，以定義網站的區段。 x-site欄位包含在輸出文字檔案的名稱中，每個檔案都包含一個日曆日的資料。

![](assets/cfg_VisualTransform_SplittingExample.png)
