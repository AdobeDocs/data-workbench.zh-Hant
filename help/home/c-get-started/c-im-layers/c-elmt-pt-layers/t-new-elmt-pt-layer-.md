---
description: 讓任何元素點圖層都可顯示在全球視覺化上的步驟。
title: 讓新的元素點層可供使用
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
exl-id: 12797335-0788-4103-a581-41bc3bb3dcc9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%

---

# 讓新的元素點層可供使用{#make-a-new-element-point-layer-available}

讓任何元素點圖層都可顯示在全球視覺化上的步驟。

1. 在Data Workbench伺服器安裝目錄的Profiles\*profile name*\Maps資料夾中，放置層檔案及其相關查找檔案。
1. 如果您為元素點圖層定義了新維度，但尚未重新轉換資料集，請立即重新轉換資料集。
1. 在「描述檔」\*描述檔名稱*\Maps資料夾中編輯[!DNL order.txt]檔案，以反映您要圖層顯示的順序。 預設情況下，圖層按其名稱以字典順序顯示。

   >[!NOTE]
   >
   >編輯[!DNL order.txt]檔案時，請注意不要遮住要顯示的地圖圖層。

   有關使用[!DNL order.txt]檔案的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中的「配置介面和分析功能」一章。

1. 在Data Workbench中，按一下右鍵工作區標題欄，然後按一下&#x200B;**[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*&#x200B;以選擇所需的配置檔案。
1. 按一下右鍵工作區標題欄，然後按一下&#x200B;**[!UICONTROL Work Online]**。 「Work Online（聯機工作）」旁邊顯示X。
1. 開啟工作區，並在全球視覺化上按一下滑鼠右鍵，然後選取新圖層。 圖層名稱旁會出現X。
