---
description: 使用「量度維度」精靈建立新的量度維度。
title: 度量維度精靈
uuid: 77b9bc8e-7625-4fef-9de4-f113f9b2debd
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# 度量維度精靈{#metric-dim-wizard}

使用「量度維度」精靈建立新的量度維度。

量度維度會將量度轉換為新維度。 例如，根據頁面檢視量度和訪客層級的量度維度，會根據每位訪客的頁面檢視總數顯示維度元素。 它可讓您根據維度元素擴充目前定義的量度，以建立並儲存為新維度。

## 步驟1:選擇維度和量度 {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. **開啟量度維度精靈**。

   在工作區中，按一下滑鼠右鍵並選取「工 **具** >建 **立量度尺寸**」。

1. **將量度命名為「尺寸」**。

   預設情況下，「名稱」欄位會根據「層級」和「量度」選擇自動填入。

1. **選擇維級別。** 維級別是包含所有組成元素值的父級維，用於篩選輸入和定義維類型。

   維級別包括：

   * 點進
   * 點擊
   * 產品
   * 瀏覽
   * 訪客

1. **選取量度**。

   選取預先建立的量度以擴充並儲存為量度尺寸。

   ![](assets/6_4_workstation_metricdim_metric.png)

1. （選用） **建立量度公式**。

   按一下方塊以輸入自訂量度公式。 將出現計算的「預覽」值，驗證表達式。

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   您可以新增自己的量 [度運算式](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) ，或從其他量度編輯器或視覺化剪下並貼上。 在精靈中會報告語法錯誤、公式錯誤、未定義的篩選器和其他錯誤。

1. 按&#x200B;**「下一步」**。

## 步驟2:格式和設定時段 {#section-5bddf3cd306545d7806a501637f80f77}

您可以選取量度格式並設定維度運算式的貯體值。

1. 為新度 **量尺寸** 選取「格式」。

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   格式定義在視覺化中開啟度量時的呈現方式。 這些格式為選 [擇的printf標準](http://www.cplusplus.com/reference/cstdio/printf/)，定義如下：

   ```
   %[flags][width][.precision][length][specifier]
   %
   0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   在「預 **覽** 」欄位中，會根據選取的量度和格式顯示值。

1. 新增 **桶計數運算** 式。

   您可以定義含有各種範圍或區間的量度維度。 這會根據大小傳回元素的子集， [例如0-4]、 [5-10]、...)。 「維度層級」的元素與範圍包含量度值的元素相關。 請參閱維度運算式語法 [中的儲存貯式說明](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html)。

1. 按一 **下「預覽** 」，在儲存前開啟「量度尺寸」值的表格。

   ![](assets/6_4_workstation_metricdim_preview.png)

   表格詳細資訊每個量度維度的量度值。

1. 按一 **下「在維度選單中顯示** 」，將新建立的維度新增至「搜尋器」的「維度 **** 」索引標籤 **中**。
1. 按&#x200B;**「下一步」**。

## 步驟3:完成並儲存 {#section-d9043235b18a425f9de0db668d4b1683}

1. 選取以在儲存後啟動「量度尺寸編輯器」、圖形視覺化或表格。

   | 欄位 | 說明 |
   |---|---|
   | 啟動量度維度編輯器 | 開啟量度維度編輯器。 |
   | 啟動圖 | 啟動表格的PNG圖形。 |
   | 啟動表 | 在工作區中啟動表格，其中欄中的值列出新量度值與所選量度值比較的值。 |

1. 按一 **下「完成** 」並儲存。

   將會開啟儲存對話方塊，讓您儲存檔案。 在工作區中將開啟選定的查看值選項。
