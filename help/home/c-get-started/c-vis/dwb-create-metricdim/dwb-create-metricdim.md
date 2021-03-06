---
description: 使用「量度維度」精靈建立新的量度Dimension。
title: 量度維度精靈
uuid: 77b9bc8e-7625-4fef-9de4-f113f9b2debd
exl-id: 109fbefc-5608-493d-aec9-8337f21eaa70
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# 量度維度精靈{#metric-dim-wizard}

使用「量度維度」精靈建立新的量度Dimension。

量度維度會將量度轉換為新維度。 例如，以頁面檢視量度和訪客層級為基礎的量度維度，會根據每個訪客的頁面檢視總數來顯示維度元素。 它可讓您根據維度元素擴充目前定義的量度，以建立並儲存為新維度。

## 步驟1:選取維度和量度 {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. **開啟量度維度精靈**。

   在工作區中，按一下右鍵並選擇「**工具** > **建立度量維**」。

1. **將量度命名為維度**。

   預設情況下，「名稱」欄位會根據「層級」和「量度」選取項目自動填入。

1. **選取Dimension層級。** 維級別是包含所有構成元素值的父維，用於篩選輸入並定義維類型。

   Dimension層級包括：

   * 點進
   * 點擊
   * 產品
   * 瀏覽
   * 訪客

1. **選取量度**。

   選取預先建立的量度以延伸並儲存為量度維度。

   ![](assets/6_4_workstation_metricdim_metric.png)

1. （選用）**建立量度公式**。

   按一下方塊以輸入自訂量度公式。 計算的「預覽」值將出現，驗證運算式。

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   您可以新增自己的[量度運算式](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)，或從其他量度編輯器或視覺效果剪下並貼上。 在精靈中會報告語法錯誤、公式錯誤、未定義的篩選器和其他錯誤。

1. 按&#x200B;**「下一步」**。

## 步驟2:格式和設定貯體 {#section-5bddf3cd306545d7806a501637f80f77}

您可以選取量度格式，並設定維度運算式的貯體值。

1. 為新度量維選擇&#x200B;**格式**。

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   格式會定義在視覺效果中開啟量度時的呈現方式。 選擇以下格式[printf標準](https://www.cplusplus.com/reference/cstdio/printf/)，定義如下：

   ```
   %[flags][width][.precision][length][specifier]
   %
   0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   在&#x200B;**預覽**&#x200B;欄位中，根據選取的度量和格式顯示值。

1. 新增&#x200B;**貯體計數**&#x200B;運算式。

   您可以定義具有各種範圍或貯體的量度維度。 這會根據大小傳回元素子集，例如[0-4]、[5-10],...)。 「Dimension層級」的元素與其範圍包含量度值的元素相關。 請參閱[Dimension運算式的語法](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html)上的貯體運算式說明。

1. 按一下「**預覽**」以在儲存前開啟「量度維度」值的表格。

   ![](assets/6_4_workstation_metricdim_preview.png)

   表格詳細資料每個量度的量度值維度。

1. 按一下「**在Dimension菜單中顯示**」，將新建立的維添加到&#x200B;**Finder**&#x200B;中的&#x200B;**Dimension**&#x200B;頁簽。
1. 按&#x200B;**「下一步」**。

## 步驟3:完成並保存 {#section-d9043235b18a425f9de0db668d4b1683}

1. 選取「 」，即可在儲存後啟動「量度維度編輯器」、「圖表視覺效果」或「表格」。

   | 欄位 | 說明 |
   |---|---|
   | 啟動量度維度編輯器 | 開啟量度維度編輯器。 |
   | 啟動圖表 | 啟動表格的PNG圖形。 |
   | 啟動表格 | 在工作區中啟動表格，列中的值會列出新量度的值，並與所選量度的值比較。 |

1. 按一下&#x200B;**完成**&#x200B;並保存。

   將會開啟儲存對話方塊，讓您儲存檔案。 將在工作區中開啟查看值的選定選項。
