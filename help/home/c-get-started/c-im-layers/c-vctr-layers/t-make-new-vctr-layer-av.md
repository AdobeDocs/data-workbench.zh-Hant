---
description: 讓任何向量層都可顯示在全球視覺效果的步驟。
title: 讓新的向量層可供使用
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 7%

---

# 讓新的向量層可供使用{#make-a-new-vector-layer-available}

讓任何向量層都可顯示在全球視覺效果的步驟。

1. 在Data Workbench伺服器安裝目錄內的Profiles\*profile name*\Maps資料夾中，放置層檔案和[!DNL .vec]或[!DNL .tsv]檔案。
1. 編輯「配置檔案」(Profiles)\*配置檔案名稱*\映射資料夾中的[!DNL order.txt]檔案，以反映要顯示圖層的順序。 預設情況下，圖層按其名稱以字典順序顯示。

   >[!NOTE]
   >
   >編輯[!DNL order.txt]檔案時，請注意不要覆蓋要顯示的映射層。

   有關使用[!DNL order.txt]檔案的詳細資訊，請參閱[使用Order.txt檔案自定義菜單](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。

1. 在Insight中，以滑鼠右鍵按一下工作區標題列，然後按一下&#x200B;**[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*，以選取所需的設定檔。
1. 以滑鼠右鍵按一下工作區標題列，然後按一下&#x200B;**[!UICONTROL Work Online]**。 「Work Online（聯機工作）」旁邊出現X。
1. 開啟工作區，並在全域視覺效果上按一下滑鼠右鍵並選取新圖層。 圖層名稱旁會出現X。
