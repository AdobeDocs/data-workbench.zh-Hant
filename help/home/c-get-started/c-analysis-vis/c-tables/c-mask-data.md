---
description: 遮色片是指選取維度中資料的子集或元素的子集。
title: 遮罩資料
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
exl-id: 3029e08e-827f-40d7-b5a1-45630876a097
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 1%

---

# 遮罩資料{#mask-data}

遮色片是指選取維度中資料的子集或元素的子集。

您可遮色或隱藏不想要包含在分析中的元素。

Data Workbench提供兩種遮色尺寸元素的方法。 第一個方法使用[!DNL Mask]功能表中的可用選項。 使用[!DNL Mask]功能表選項，您可以使用滑鼠來選取要顯示或遮色的元素，或在依量度排序資料時顯示排名最前的元素。 第二種用於遮蔽尺寸元素的方法採用搜索。

**若要遮色資料**

1. 按一下右鍵所需維的元素或標籤，然後按一下&#x200B;**[!UICONTROL Mask]**。

   ![](assets/mnu_Table_Mask.png)

1. 按一下下列其中一個選項:

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]**，或依 **[!UICONTROL 500]** 量度排序的顯示元素
   * **[!UICONTROL Show top > All Positive]** 僅顯示大於零(0)的值
   * **[!UICONTROL Display “X more”]** 顯示目前被遮色片的元素數
   * **[!UICONTROL At least one >]***&lt;>>*（僅當使用非正規維度時可用）**[!UICONTROL countable dimension name]**

      使用非正規維度時，此選項可讓您以可計數的維度遮色。 選中後，表格僅顯示那些至少具有所選可計數維中一個元素的元素。 表格最多顯示1,023個元素。

>[!NOTE]
>
>由於Adobe[!DNL Platform]以隨機順序處理資料，因此當至少一個遮色片產生超過1,023個元素時，較常見和較大的元素更有可能被納入表格中。

當您依「顯示頂端」或「至少一個」遮色時，依預設，表格中的順序會與當時選取範圍所影響的值相對應。 如果您稍後更改選擇，則順序不會從原始順序更改，除非使用表或啟用「動態選擇」。 按一下&#x200B;**[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**&#x200B;時，每次更改選擇時都會重複使用表。

**使用搜尋來遮色資料**

* 您可以使用下列任一搜尋選項來遮色資料：

   * 按一下右鍵所需維的元素或標籤，按一下&#x200B;**[!UICONTROL Mask]** ，然後在[!DNL Search]框中鍵入要搜索的片語。

      ![](assets/mnu_Table_MaskSearch.png)

   * 按一下右鍵所需維的元素或標籤，按一下&#x200B;**[!UICONTROL Mask]** > **[!UICONTROL Display search bar]** ，然後在維標籤單元格中顯示的搜索框中鍵入要搜索的短語。

      ![](assets/vis_Table_Mask_searchBar.png)

      當您輸入搜尋片語時，Data Workbench會更新維度以反映相符項目。

若要在搜尋期間進一步限制遮色片，可使用下列任一方法：

* 您可以在[!DNL search]方塊或列中輸入&quot;re:&quot;，讓搜尋片語解譯為規則運算式。 您可以在搜尋片語中使用與規則運算式關聯的任何語法。 有關規則運算式的詳細資訊，請參閱&#x200B;*資料集配置指南*&#x200B;中的「規則運算式」附錄。
* 您可以鍵入$符號作為搜尋字串中的第一個字元，以尋找以您輸入的字串開頭的片語，或是以您輸入的字串結尾的片語。
* 您可以鍵入空格作為搜索字串中的第一個字元，以查找以輸入的字串開頭的短語中的任何單詞，或鍵入最後一個字元以查找以輸入的字串結尾的短語中的任何單詞。

以下是使用搜尋中的字串&quot;on&quot;遮色表格的不同方法範例：

* 鍵入&quot;on&quot;會顯示每個包含字串&quot;on&quot;的片語：「**線路銀行」、「c**&#x200B;機動買家」、「硬幣上的bulli **、「行上的a6/」、「金opti**&#x200B;在&#x200B;**s上的gold opti8/>、「銀幣**」11/>.&quot;************
* 輸入&quot;$on&quot;會顯示以字串&quot;on&quot;開頭的每個片語：

   「**on** line banking」和「**on**-line payment」。

* 鍵入&quot;on$&quot;會顯示以字串&quot;on&quot;結尾的每個片語：

   「silver bulli **on**」和「gold opti **on**」。

* 鍵入&quot;on&quot;會顯示每個包含以字串&quot;on&quot;開頭的字詞的片語：

   「**on** line banking」和「bank **on** line」。

* 鍵入&quot;on&quot;會顯示每個包含以字串&quot;on&quot;結尾之字詞的片語：

   「bulli **on↑[a1/]coins」和「silver bulli** on↑[a3/]」。****

* 使用&quot;on&quot;會將包含字串&quot;on&quot;的每個片語顯示為單字：

   「**on**&#x200B;行銀行」和「bank **on**&#x200B;行」。
