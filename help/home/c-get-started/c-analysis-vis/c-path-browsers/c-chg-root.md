---
description: 您可以指定顯示的元素為根，或將新元素新增至視覺效果，以變更路徑瀏覽器的根。
title: 變更路徑瀏覽器的根目錄
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
exl-id: 09842b93-af26-42b9-9395-a02b86978b21
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# 變更路徑瀏覽器的根目錄{#change-the-path-browser-s-root}

{{eol}}

您可以指定顯示的元素為根，或將新元素新增至視覺效果，以變更路徑瀏覽器的根。

>[!NOTE]
>
>不能將起始節點或終止節點設定為路徑瀏覽器的根節點。

**設定路徑瀏覽器的根目錄**

* 以滑鼠右鍵按一下所需的元素，然後按一下 **[!UICONTROL Set as root]**.

**新增元素至路徑瀏覽器的方式**

1. 開啟一個圖形或表格，顯示要在路徑瀏覽器上顯示其元素的維。

   例如，如果您使用網站資料，請開啟頁面圖表或表格，並識別您要設定為根的頁面。

1. 按Ctrl+Alt並將所需元素拖曳至路徑瀏覽器上的根位置。

   >[!NOTE]
   >
   >您可以將所需維度的元素拖曳至路徑瀏覽器，以變更與路徑瀏覽器相關聯的基本維度。 此元素會成為路徑瀏覽器的新根，而路徑瀏覽器左上角的標籤會變更，以反映此元素的維度。

   例如，假設您建立一個頁面路徑瀏覽器，顯示每個工作階段的頁面順序。 如果您要將「搜尋詞」維度的元素拖曳至路徑瀏覽器，搜尋詞元素將成為新的根，標籤現在會顯示每個工作階段的搜尋詞順序。

   >[!NOTE]
   >
   >將元素拖曳至路徑瀏覽器可能會變更與路徑瀏覽器相關聯的基本維度，但不會變更層級維度、群組維度或量度。 因此，在選擇與路徑瀏覽器的層級維度、群組維度和量度搭配使用時，您必須小心選擇有意義的基本維度。 若要變更層級維度、群組維度或量度，您必須編輯路徑瀏覽器的 [!DNL *.vw] 檔案（如記事本）。 請參閱 [配置路徑瀏覽器](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
