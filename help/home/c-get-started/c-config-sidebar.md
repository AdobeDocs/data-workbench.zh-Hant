---
description: 側邊欄提供對定期使用函式的存取，並可在您在工作區之間移動時保留視覺效果。
title: 設定側欄
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
exl-id: 75ccc869-8ced-4beb-b3d7-ed7febe347f9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# 設定側欄{#configure-the-sidebar}

{{eol}}

側邊欄提供對定期使用函式的存取，並可在您在工作區之間移動時保留視覺效果。

管理員可以自訂側欄，使其適合不同的使用者群組，然後使用設定檔部署側欄。

側邊欄是協助您追蹤篩選器和本機覆寫的理想選擇。 如果您不想使用側欄，可以隱藏它。

## 新增視覺效果至側欄 {#section-666f70a405db4f8d8eaffa567ffcac06}

1. 啟動Data Workbench。
1. 在側欄中，按一下 **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*. 例如 [!DNL Selections Panel]、[!DNL Filters Panel] 或 [!DNL Table]。

   標準安裝中提供下列邊欄面板。Data Workbench 您的特定設定檔中可能會有更多項目可用：

   * **選擇面板：** 可讓您了解目前工作區中作用中的選取項目。 此 [!DNL Selections Panel] 會在您進行新選取時更新。 您可以按一下 **[!UICONTROL x]**. 請參閱 [在視覺效果中進行選取](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) ，了解如何選取資料。
   * **篩選器面板：** 可輕鬆載入及套用儲存的篩選。 您可以載入多個篩選器，並按一下篩選器旁的核取方塊，以個別啟用或停用每個篩選器。 請參閱 [篩選器編輯器](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **本地覆蓋面板：** 此面板會顯示設定檔中顯示的量度、維度和篩選器，已在您的個人設定檔副本中修改。 這有助於提醒您，資料在用戶端中的顯示方式與其他使用者之間可能會有差異。 將量度、維度或篩選器中的變更儲存至伺服器時，覆寫會從 [!DNL Local Overrides panel]. 如果您按一下覆寫，然後按一下 **[!UICONTROL Revert to Server]**，本機覆寫即會移除，項目會回復為共用版本。
   * **量度圖例：** 新增量度圖例。 [!DNL Metric legends] 可讓您查看與設定檔相關的基線量度，以及與資料集相關的統計資料(或與目前選取項目相關的統計資料（如果已選取）)。 請參閱 [量度圖例](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
   * **色彩圖例：** 新增顏色圖例。 您可以依量度（例如轉換和保留）將視覺化色彩碼視覺化，並在幾乎每個項目中使用 [!DNL Workspace]. 將業務量度連結至顏色可讓您輕鬆找出異常、例外和趨勢。 請參閱 [色彩圖例](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).
   * **文本注釋：** 新增附註面板。 [!DNL Text annotations] 是可在其中輸入任意文本以向其中添加描述性資訊或注釋的窗口 [!DNL Workspace]. 請參閱 [使用文字註解](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * **表：** 新增表格。 表格可在一或多個資料維度上顯示一或多個量度。 請參閱 [表格](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **開啟：** 開啟儲存的檔案。

## 開啟側欄面板 {#section-cbc8e57491854274a577d47a48c306b8}

您可以從儲存的位置或剪貼簿開啟側欄視覺效果檔案。

1. 在側欄中，按一下 **[!UICONTROL Add]** > **[!UICONTROL Open]**.
1. 按一下 **[!UICONTROL File]** 若要找出 [!DNL .vw] 要添加的面板的檔案，或按一下 **[!UICONTROL Last Closed Window]**，可從剪貼簿提取視覺效果。

   此外，您可以按一下 **[!UICONTROL From Clipboard]** 貼上已複製到剪貼簿的視覺效果。 請參閱 [複製側欄面板](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1).

## 複製側欄面板 {#section-720ae057632a4b8dbb94412e06a370b1}

1. 以滑鼠右鍵按一下面板的上方邊框，然後按一下 **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. 若要貼上面板，請按一下 **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## 保存側欄面板 {#section-fb19936b12704fb0a4c592abb579db1d}

在側欄面板上，以滑鼠右鍵按一下標題列中的，然後按一下 **[!UICONTROL Save]**.

同樣地，您也可以開啟儲存的側欄視覺效果。 Data Workbench會將視覺效果儲存為 [!DNL .vw] 檔案。

## 還原為預設側欄 {#section-4d14b8771ad747bba799876267f24831}

在側欄中，按一下 **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

當您關閉Data Workbench時，系統會將目前的側欄設定儲存在 [!DNL sidebar.vw] 檔案。 當您開啟Data Workbench時，系統會載入 [!DNL sidebar.vw] 檔案，而非父設定檔。

您可以回復為預設或先前儲存的側欄，這會從使用者設定檔刪除側欄，並從上層設定檔重新載入側欄。 管理員可以從上傳預設（上層）側欄，將其取代為本機側欄 [!DNL Profile Manager].

## 自訂更多狀態面板檔案 {#section-8d502f3b59cc4331966edec05e896ce1}

系統管理員可在 [!DNL More Status Panel.vw]. 這會將量度和維度值放在相關的內容字詞，並在 [!DNL More Status panel] 欄。

若要顯示 [!DNL More Status panel] 在側欄中，按一下以下示例中所示的箭頭。

![](assets/more_status_panel_arrows.png)

以下程式示範如何建立自訂狀態的簡單範例，告訴您資料集中有多少天：

1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Sidebar\]**.

1. 在 [!DNL Base_5_3*] 欄，建立本機副本 [!DNL More Status Panel.vw] 檔案。

   若要這麼做，請以滑鼠右鍵按一下檔案勾號，然後按一下 **[!UICONTROL Make Local]**.

1. 開啟 [!DNL More Status Panel.vw] 檔案 [!DNL .vw] [!DNL Editor] 或記事本。

   ![](assets/more_status_panel_file.png)

1. 完成 [!DNL Context] 和 [!DNL Items] 欄位 [!DNL Editor]. 請參閱 [查詢語言語法](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) 以取得語法的相關准則。

1. 儲存檔案。

   上例中的值會產生如下所示的狀態公式：

   ![](assets/more_status_panel.png)
