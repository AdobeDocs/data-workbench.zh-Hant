---
description: 讓元素點圖層可在全球視覺化中顯示的步驟。
title: 讓新的元素點層可供使用
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
exl-id: 9001f6b6-5d25-48a0-9381-04f679e0ff4d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%

---

# 讓新的元素點層可供使用{#making-a-new-element-point-layer-available}

讓元素點圖層可在全球視覺化中顯示的步驟。

1. 在資料工作台伺服器安裝目錄的「描述檔名稱*\Maps」資料夾中，放置圖層檔案及其相關查閱檔案。
1. 如果您為元素點圖層定義了新維度，但尚未重新轉換資料集，請立即重新轉換資料集。
1. 在「描述檔」\*描述檔名稱*\Maps資料夾中編輯[!DNL order.txt]檔案，以反映您要圖層顯示的順序。 預設情況下，圖層按其名稱以字典順序顯示。

   >[!NOTE]
   >
   >編輯[!DNL order.txt]檔案時，請注意不要遮住要顯示的地圖圖層。

   有關使用[!DNL order.txt]檔案的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中的「配置介面和分析功能」一章。

1. 在資料工作台中，以滑鼠右鍵按一下工作區標題列，然後按一下&#x200B;**[!UICONTROL Switch Profile]** > ***[!UICONTROL profile name]**>*，以選取所要的描述檔。
1. 按一下右鍵工作區標題欄，然後按一下&#x200B;**[!UICONTROL Work Online]**。 [!DNL Work Online]旁邊會出現X。
1. 開啟工作區，並在全球視覺化上按一下滑鼠右鍵，然後選取新圖層。 圖層名稱旁會出現X。
