---
description: 使用逐步嚮導建立由度量屬性（度量維度）定義的Dimension。 然後test、預覽並將新的「度量尺寸」保存到Dimension清單。
title: 度量維度嚮導(Dimension)
uuid: 411b2e28-0958-43bb-a853-7de7b3063818
exl-id: 4d283a00-409c-4d74-a558-40744caba71c
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 2%

---

# 量度維度精靈{#metric-dim-wizard}

使用逐步嚮導建立由度量屬性（度量維度）定義的Dimension。 然後test、預覽並將新的「度量尺寸」保存到Dimension清單。

度量維度將度量轉換為新維度。 例如，基於頁面視圖度量和訪問者級別的度量維度將根據每個訪問者的頁面視圖總數顯示維度元素。 它允許您根據維元素擴展當前定義的度量，以建立並另存為新維。

## 步驟1:選擇Dimension和度量 {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. 開啟度量維度嚮導。

   在工作區中，按一下右鍵並選擇 **[!UICONTROL Tools]** > **[!UICONTROL Create Metric Dim]**。

1. 命名度量維度。

   預設情況下，「名稱」欄位將基於「級別」和「度量」選擇自動填充。

1. 選擇Dimension級別。

   維級別是包含所有組成元素值的父維，用於篩選輸入並定義維類型。

   Dimension級別包括：

   * 點擊
   * 點擊
   * 產品
   * 瀏覽
   * 訪客

1. 選擇度量。

   選擇預構建的度量以擴展並另存為度量維度。

   ![](assets/6_4_workstation_metricdim_metric.png)

1. （可選）建立度量公式。

   按一下該框以輸入自定義度量公式。 將出現計算的「預覽」(Preview)值，驗證表達式。

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   您可以添加自己的 [度量表達式](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) 或從其他度量編輯器或可視化中剪切和貼上。 嚮導中報告語法錯誤、公式錯誤、未定義的篩選器和其他錯誤。

1. 按一下 **[!UICONTROL Next]**。

## 步驟2:格式和設定儲存段 {#section-5bddf3cd306545d7806a501637f80f77}

1. 選擇新度量尺寸的格式。

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   該格式定義在可視化中開啟度量時將如何顯示度量。 選擇了這些格式 [printf標準](https://www.cplusplus.com/reference/cstdio/printf/)，定義如下：

   ```
   %[flags][width][.precision][length][specifier]
   % 0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   在 **[!UICONTROL Preview]** 欄位中，將根據選定的度量和格式顯示一個值。

1. 添加桶計數表達式。

   您可以定義具有各種範圍或時段的度量維度。 這將返回基於大小的元素子集，如 [0-4]。 [5-10],...) Dimension級別的元素與其範圍包含度量值的元素相關。 請參閱以下位置的儲存桶表達式說明 [Dimension表達式的語法](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html)。

1. 按一下 **[!UICONTROL Preview]** 以在保存前開啟度量維度值表。

   ![](assets/6_4_workstation_metricdim_preview.png)

   表詳細列出每個度量維度的度量值。

1. 按一下 **[!UICONTROL Show in Dimension Menu]** 將新建立的維添加到 **Dimension** 的 **查找器**。

1. 按一下 **[!UICONTROL Next]**。

## 第3步：完成並保存 {#section-d9043235b18a425f9de0db668d4b1683}

1. 選擇以在保存後啟動度量尺寸編輯器、圖形可視化或表。

   | 欄位 | 說明 |
   |---|---|
   | **[!UICONTROL Launch Metric Dim Editor]** | 開啟度量維度編輯器。 |
   | **[!UICONTROL Launch Graph]** | 啟動表的PNG圖形。 |
   | **[!UICONTROL Launch Table]** | 在工作區中啟動一個表，其中列中的值列出與所選度量的值相比的新度量維度的值。 |

1. 按一下 **[!UICONTROL Finish]** 然後保存。

   將開啟一個保存對話框，允許您保存檔案。 將在工作區中開啟用於查看值的選定選項。
