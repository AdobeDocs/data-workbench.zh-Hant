---
description: 讓任何元素點層都可顯示在全球視覺效果的步驟。
title: 讓新的元素點層可供使用
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
exl-id: 12797335-0788-4103-a581-41bc3bb3dcc9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%

---

# 讓新的元素點層可供使用{#make-a-new-element-point-layer-available}

{{eol}}

讓任何元素點層都可顯示在全球視覺效果的步驟。

1. 在Data Workbench伺服器安裝目錄內的配置檔案\*配置檔案名稱*\映射資料夾中，放置圖層檔案及其相關的查找檔案。
1. 如果您為元素點層定義了新維度，但尚未重新轉換資料集，請立即重新轉換資料集。
1. 編輯 [!DNL order.txt] 檔案，以反映圖層的顯示順序。 預設情況下，圖層按其名稱以字典順序顯示。

   >[!NOTE]
   >
   >編輯 [!DNL order.txt] 檔案中，請注意不要覆蓋要顯示的地圖層。

   如需使用的詳細資訊 [!DNL order.txt] 檔案，請參閱 *Data Workbench使用手冊*.

1. 在Data Workbench中，以滑鼠右鍵按一下工作區標題列，然後按一下，以選取所需的設定檔 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. 以滑鼠右鍵按一下工作區標題列，然後按一下 **[!UICONTROL Work Online]**. 「Work Online（聯機工作）」旁邊出現X。
1. 開啟工作區，並在全域視覺效果上按一下滑鼠右鍵並選取新圖層。 圖層名稱旁會出現X。
