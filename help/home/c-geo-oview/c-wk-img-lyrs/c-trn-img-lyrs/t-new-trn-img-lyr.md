---
description: 讓新地形圖層可在全球視覺化中顯示的步驟。
solution: Analytics
title: 使新的地形圖層可用
topic: Data workbench
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使新的地形圖層可用{#making-a-new-terrain-image-layer-available}

讓新地形圖層可在全球視覺化中顯示的步驟。

1. 在安裝目錄的Profiles\*profile name*\Maps資料夾中， **[!UICONTROL Insight Server]** 放置圖層檔案和支援映像檔案。
1. 在「描 [!DNL order.txt] 述檔名*\地圖」資料夾中編輯檔案，以反映您要圖層顯示的順序。 預設情況下，圖層按其名稱以字典順序顯示。

   >[!NOTE]
   >
   >編輯檔 [!DNL order.txt] 案時，請小心不要遮住您要顯示的地圖圖層。

   如需使用檔案的詳 [!DNL order.txt] 細資訊，請參閱資料工作台使用指南的「設定介 *面和分析功能」一章*。

1. 在資料工作台中，以滑鼠右鍵按一下工作區標題列，然後按一下 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>以選取所要的描述檔*。
1. 在工作區標題列上按一下滑鼠右鍵，然後按一下 **[!UICONTROL Work Online]**。 X出現在旁邊 [!DNL Work Online]。
1. 開啟工作區，並在全球視覺化上按一下滑鼠右鍵並選取新圖層。 圖層名稱旁會出現X。
