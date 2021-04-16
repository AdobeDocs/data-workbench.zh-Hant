---
description: 讓新地形圖層可在全球視覺化中顯示的步驟。
title: 讓新的地形影像層可供使用
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 7%

---

# 讓新的地形影像層可供使用{#making-a-new-terrain-image-layer-available}

讓新地形圖層可在全球視覺化中顯示的步驟。

1. 在&#x200B;**[!UICONTROL Insight Server]**&#x200B;安裝目錄的Profiles\*profile name*\Maps資料夾中，放置圖層檔案和支援映像檔案。
1. 在「描述檔」\*描述檔名稱*\Maps資料夾中編輯[!DNL order.txt]檔案，以反映您要圖層顯示的順序。 預設情況下，圖層按其名稱以字典順序顯示。

   >[!NOTE]
   >
   >編輯[!DNL order.txt]檔案時，請注意不要遮住要顯示的地圖圖層。

   有關使用[!DNL order.txt]檔案的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中的「配置介面和分析功能」一章。

1. 在資料工作台中，以滑鼠右鍵按一下工作區標題列，然後按一下&#x200B;**[!UICONTROL Switch Profile]** > ***[!UICONTROL profile name]**>*，以選取所要的描述檔。
1. 按一下右鍵工作區標題欄，然後按一下&#x200B;**[!UICONTROL Work Online]**。 [!DNL Work Online]旁邊會出現X。
1. 開啟工作區，並在全球視覺化上按一下滑鼠右鍵，然後選取新圖層。 圖層名稱旁會出現X。
