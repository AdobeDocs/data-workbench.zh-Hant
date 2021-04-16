---
description: 邊欄可讓您存取常用的功能，並在您在工作區間移動時保留視覺化。
title: 設定側欄
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
exl-id: 75ccc869-8ced-4beb-b3d7-ed7febe347f9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# 設定側欄{#configure-the-sidebar}

邊欄可讓您存取常用的功能，並在您在工作區間移動時保留視覺化。

管理員可以自訂邊欄，使其適合不同的使用者群組，然後使用描述檔部署側邊欄。

側欄最適合協助您追蹤篩選器和本機覆寫。 如果您不想使用邊欄，可以將其隱藏。

## 新增視覺化至邊欄{#section-666f70a405db4f8d8eaffa567ffcac06}

1. 啟動Data Workbench。
1. 在側欄中，按一下&#x200B;**[!UICONTROL Add]** > ***[!UICONTROL item]**>*。 例如 [!DNL Selections Panel]、[!DNL Filters Panel] 或 [!DNL Table]。

   標準安裝Data Workbench中提供下列邊欄面板。 您的特定設定檔中可能會有更多項目：

   * **選取範圍面板：** 可讓您瞭解目前工作區中作用中的選取範圍。每當您進行新選擇時，[!DNL Selections Panel]就會更新。 按一下&#x200B;**[!UICONTROL x]**&#x200B;可以清除選擇。 如需如何選取資料的詳細資訊，請參閱「在視覺化中選取」[。](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746)
   * **濾鏡面板：** 可輕鬆載入和套用儲存的濾鏡。您可以載入多個篩選器，並按一下其旁的核取方塊，以個別啟用或停用每個篩選器。 請參閱[篩選編輯器](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3)。
   * **本機覆寫面板：** 此面板顯示在個人資料副本中已修改描述檔中的量度、維度和篩選器。這有助於提醒您，您的用戶端和其他使用者的資料顯示方式可能有差異。 將度量、維度或篩選條件中的變更儲存至伺服器時，會從[!DNL Local Overrides panel]移除覆寫。 如果您按一下覆寫，然後按一下&#x200B;**[!UICONTROL Revert to Server]**，就會移除本機覆寫，項目會回復為共用版本。
   * **量度圖例：** 新增量度圖例。[!DNL Metric legends] 可讓您查看與您的設定檔相關的基準量度和與資料集相關的統計資料(或是與目前選取範圍相關的基準量度（如果已建立）。請參閱[量度圖例](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b)。
   * **顏色圖例：** 新增顏色圖例。您可以依量度（例如轉換和保留）為視覺化色彩編碼，並且幾乎在每個[!DNL Workspace]中使用。 將業務量度連結至顏色，可輕鬆發現異常、例外和趨勢。 請參閱[顏色圖例](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)。
   * **文本注釋：** 添加註釋面板。[!DNL Text annotations] 是可在其中輸入任意文本的窗口，以向中添加描述性資訊或注釋 [!DNL Workspace]。請參閱[使用文本注釋](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777)。
   * **表：** 添加表。表格可以在一或多個資料維度上顯示一或多個度量。 請參閱[表](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f)。
   * **開啟：** 開啟儲存的檔案。

## 開啟側欄面板{#section-cbc8e57491854274a577d47a48c306b8}

您可以從儲存的位置或剪貼簿中開啟邊欄視覺化檔案。

1. 在側欄中，按一下「**[!UICONTROL Add]** > **[!UICONTROL Open]**」。
1. 按一下&#x200B;**[!UICONTROL File]**&#x200B;以找出您要新增之面板的[!DNL .vw]檔案，或按一下&#x200B;**[!UICONTROL Last Closed Window]**，從剪貼簿提取視覺化。

   此外，您可以按一下&#x200B;**[!UICONTROL From Clipboard]**，貼上已複製至剪貼簿的視覺化。 請參閱[複製側欄面板](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1)。

## 複製邊欄面板{#section-720ae057632a4b8dbb94412e06a370b1}

1. 以滑鼠右鍵按一下面板的上方邊框，然後按一下&#x200B;**[!UICONTROL Copy]** > **[!UICONTROL Window]**。
1. 若要貼上面板，請按一下&#x200B;**[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**。

## 保存邊欄面板{#section-fb19936b12704fb0a4c592abb579db1d}

在側欄面板上，在標題列中按一下滑鼠右鍵，然後按一下&#x200B;**[!UICONTROL Save]**。

同樣地，您也可以開啟儲存的側欄視覺化。 Data Workbench會在您指定的位置將視覺化儲存為[!DNL .vw]檔案。

## 還原為預設側欄{#section-4d14b8771ad747bba799876267f24831}

在側欄中，按一下「**[!UICONTROL Options]** > **[!UICONTROL Revert]**」。

當您關閉Data Workbench時，系統會將當前側欄配置保存在用戶配置檔案的[!DNL sidebar.vw]檔案中。 當您開啟Data Workbench時，系統會從使用者描述檔載入[!DNL sidebar.vw]檔案，而非從上層描述檔。

您可以回復為預設或先前儲存的側欄，此側欄會從使用者描述檔中刪除側欄，並從上層描述檔重新載入側欄。 管理員可從[!DNL Profile Manager]上傳預設（父）側欄，以本機側欄取代。

## 自定義更多狀態面板檔案{#section-8d502f3b59cc4331966edec05e896ce1}

系統管理員可以在[!DNL More Status Panel.vw]中建立公式。 這會將量度和維度值放在相關內容字詞旁，並在側欄的[!DNL More Status panel]中顯示結果。

若要在側欄中顯示[!DNL More Status panel]，請按一下下列範例中顯示的箭頭。

![](assets/more_status_panel_arrows.png)

下列程式顯示如何建立自訂狀態的簡單範例，告訴您資料集中有多少天：

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Sidebar\]**。

1. 在[!DNL Base_5_3*]欄中，製作[!DNL More Status Panel.vw]檔案的本機副本。

   若要這麼做，請以滑鼠右鍵按一下檔案核取標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。

1. 在[!DNL .vw] [!DNL Editor]或記事本中開啟[!DNL More Status Panel.vw]檔案。

   ![](assets/more_status_panel_file.png)

1. 填寫[!DNL Editor]中的[!DNL Context]和[!DNL Items]欄位。 有關語法的指導，請參見[查詢語言語法](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)。

1. 儲存檔案。

   前面示例中的值會生成如下所示的狀態公式：

   ![](assets/more_status_panel.png)
