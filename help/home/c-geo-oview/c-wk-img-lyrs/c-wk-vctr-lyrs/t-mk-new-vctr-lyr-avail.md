---
description: 讓向量層可用於在全球視覺效果上顯示的步驟。
title: 讓新的向量層可供使用
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 6%

---

# 讓新的向量層可供使用{#making-a-new-vector-layer-available}

{{eol}}

讓向量層可用於在全球視覺效果上顯示的步驟。

1. 在Data Workbench伺服器安裝目錄的Profiles\*profile name*\Maps資料夾中，放置圖層檔案和 [!DNL .vec] 或 [!DNL .tsv] 檔案。
1. 編輯 [!DNL order.txt] 檔案，以反映圖層的顯示順序。 預設情況下，圖層按其名稱以字典順序顯示。

   >[!NOTE]
   >
   >編輯 [!DNL order.txt] 檔案中，請注意不要覆蓋要顯示的地圖層。

   如需使用的詳細資訊 [!DNL order.txt] 檔案，請參閱 *Data Workbench使用手冊*.

1. 在Data Workbench中，以滑鼠右鍵按一下工作區標題列，然後按一下，以選取所需的設定檔 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. 以滑鼠右鍵按一下工作區標題列，然後按一下 **[!UICONTROL Work Online]**. 旁邊會出現X [!DNL Work Online].
1. 開啟工作區，並在全域視覺效果上按一下滑鼠右鍵並選取新圖層。 圖層名稱旁會出現X。
