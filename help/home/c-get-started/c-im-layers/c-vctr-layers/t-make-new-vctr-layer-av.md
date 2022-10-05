---
description: 讓任何向量層都可顯示在全球視覺效果的步驟。
title: 讓新的向量層可供使用
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 7%

---

# 讓新的向量層可供使用{#make-a-new-vector-layer-available}

{{eol}}

讓任何向量層都可顯示在全球視覺效果的步驟。

1. 在Data Workbench伺服器安裝目錄的Profiles\*profile name*\Maps資料夾中，放置圖層檔案和 [!DNL .vec] 或 [!DNL .tsv] 檔案。
1. 編輯 [!DNL order.txt] 檔案，以反映圖層的顯示順序。 預設情況下，圖層按其名稱以字典順序顯示。

   >[!NOTE]
   >
   >編輯 [!DNL order.txt] 檔案中，請注意不要覆蓋要顯示的地圖層。

   如需使用的詳細資訊 [!DNL order.txt] 檔案，請參閱 [使用Order.txt檔案自訂功能表](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. 在Insight中，以滑鼠右鍵按一下工作區標題列，然後按一下，以選取所需的設定檔 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. 以滑鼠右鍵按一下工作區標題列，然後按一下 **[!UICONTROL Work Online]**. 「Work Online（聯機工作）」旁邊出現X。
1. 開啟工作區，並在全域視覺效果上按一下滑鼠右鍵並選取新圖層。 圖層名稱旁會出現X。
