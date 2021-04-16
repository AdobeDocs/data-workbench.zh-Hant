---
description: 讓任何地形圖層都可在全球視覺化上顯示的步驟。
title: 讓新的地形影像層可供使用
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
exl-id: bf0e6b37-4c8a-4d50-8bc9-eb70ca1cbb23
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 7%

---

# 讓新的地形影像層可供使用{#make-a-new-terrain-image-layer-available}

讓任何地形圖層都可在全球視覺化上顯示的步驟。

1. 在Data Workbench伺服器安裝目錄的Profiles\*profile name*\Maps資料夾中，放置層檔案和支援映像檔案。
1. 在「描述檔」\*描述檔名稱*\Maps資料夾中編輯[!DNL order.txt]檔案，以反映您要圖層顯示的順序。 預設情況下，圖層按其名稱以字典順序顯示。

   >[!NOTE]
   >
   >編輯[!DNL order.txt]檔案時，請注意不要遮住要顯示的地圖圖層。

   有關使用[!DNL order.txt]檔案的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中的「配置介面和分析功能」一章。

1. 在Data Workbench中，按一下右鍵工作區標題欄，然後按一下&#x200B;**[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*&#x200B;以選擇所需的配置檔案。
1. 按一下右鍵工作區標題欄，然後按一下&#x200B;**[!UICONTROL Work Online]**。 「Work Online（聯機工作）」旁邊顯示X。
1. 開啟工作區，並在全球視覺化上按一下滑鼠右鍵，然後選取新圖層。 圖層名稱旁會出現X。
