---
description: 讓元素點圖層可在全球視覺化中顯示的步驟。
solution: Analytics
title: 使新元素點層可用
topic: Data workbench
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使新元素點層可用{#making-a-new-element-point-layer-available}

讓元素點圖層可在全球視覺化中顯示的步驟。

1. 在資料工作台伺服器安裝目錄的「描述檔名稱*\Maps」資料夾中，放置圖層檔案及其相關查閱檔案。
1. 如果您為元素點圖層定義了新維度，但尚未重新轉換資料集，請立即重新轉換資料集。
1. 在「描 [!DNL order.txt] 述檔名*\地圖」資料夾中編輯檔案，以反映您要圖層顯示的順序。 預設情況下，圖層按其名稱以字典順序顯示。

   >[!NOTE]
   >
   >編輯檔 [!DNL order.txt] 案時，請小心不要遮住您要顯示的地圖圖層。

   如需使用檔案的詳 [!DNL order.txt] 細資訊，請參閱資料工作台使用指南的「設定介 *面和分析功能」一章*。

1. 在資料工作台中，以滑鼠右鍵按一下工作區標題列，然後按一下 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>以選取所要的描述檔*。
1. 在工作區標題列上按一下滑鼠右鍵，然後按一下 **[!UICONTROL Work Online]**。 X出現在旁邊 [!DNL Work Online]。
1. 開啟工作區，並在全球視覺化上按一下滑鼠右鍵並選取新圖層。 圖層名稱旁會出現X。
