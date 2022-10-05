---
description: 遮罩是指選取資料的子集或維度中元素的子集。
title: 遮罩資料
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
exl-id: 3029e08e-827f-40d7-b5a1-45630876a097
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 1%

---

# 遮罩資料{#mask-data}

{{eol}}

遮罩是指選取資料的子集或維度中元素的子集。

您可以遮罩或隱藏不想包含在分析中的元素。

Data Workbench提供兩種遮蔽維元素的方法。 第一個方法採用 [!DNL Mask] 功能表。 使用 [!DNL Mask] 功能表選項，您可以使用滑鼠來選取要顯示或要遮罩的元素，或在依量度排序資料時顯示排名最前的元素。 用於遮蔽尺寸元素的第二方法採用搜索。

**遮罩資料**

1. 以滑鼠右鍵按一下所需維度的元素或標籤，然後按一下 **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. 按一下下列其中一個選項:

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]**，或 **[!UICONTROL 500]** 依量度排序的顯示元素
   * **[!UICONTROL Show top > All Positive]** 僅顯示大於零的值(0)
   * **[!UICONTROL Display “X more”]** 顯示當前被遮罩的元素數
   * **[!UICONTROL At least one >]***&lt; **[!UICONTROL countable dimension name]**>*（僅適用於非正規維度）

      使用非正規維度時，此選項可讓您以可數維度來遮罩維度。 選取後，表格只會顯示至少有一個元素屬於您選取之可數維度。 表格最多可顯示1,023個元素。

>[!NOTE]
>
>因為Adobe [!DNL Platform] 以隨機順序處理資料，當至少一個掩碼產生1,023個以上的元素時，較常見和較大的元素有更大的機會被包括在表中。

當您按「顯示頂部」或「至少一個」遮罩時，預設情況下，表格中的順序與當時受選擇影響的值相對應。 如果以後更改選擇，則順序不會從原始順序更改，除非使用表或啟用「動態選擇」。 當您按一下 **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**，則每次變更選取項目時，都會重複使用表格。

**使用搜尋來遮罩資料**

* 您可以使用下列任一搜尋選項來遮罩資料：

   * 以滑鼠右鍵按一下所需維度的元素或標籤，然後按一下 **[!UICONTROL Mask]**，然後在 [!DNL Search] 框鍵入要搜索的短語。

      ![](assets/mnu_Table_MaskSearch.png)

   * 以滑鼠右鍵按一下所需維度的元素或標籤，然後按一下 **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]**，然後在維度標籤儲存格中顯示的搜尋方塊中，輸入您要搜尋的片語。

      ![](assets/vis_Table_Mask_searchBar.png)

      當您輸入搜尋片語時，Data Workbench會更新維度以反映相符項目。

要在搜索期間進一步限制掩碼，可以使用下列任一方法：

* 您可以在 [!DNL search] 方塊或長條，將搜尋詞解譯為規則運算式。 您可以在搜尋片語中使用與規則運算式相關聯的任何語法。 如需規則運算式的詳細資訊，請參閱 *資料集組態指南*.
* 您可以在搜索字串中鍵入$符號作為第一個字元，以查找以您輸入的字串開頭的短語，或鍵入為最後一個字元以查找以輸入的字串結尾的短語。
* 您可以在搜索字串中鍵入空格作為第一個字元，以查找短語中以您輸入的字串開頭的任何單詞，或鍵入最後一個字元作為查找短語中以您輸入的字串結尾的任何單詞。

以下是在搜尋中使用字串「on」來遮罩表格的不同方式範例：

* 鍵入&quot;on&quot;會顯示每個片語中包含字串&quot;on&quot;的片語：&quot;**on**&#x200B;線上銀行，&quot; &quot;c **on**&#x200B;碰頭買家，」布爾利&#x200B;**on** 硬幣，銀行 **on** line,&quot;, &quot;gold opti **on** s和silver bulli **on**.&quot;
* 鍵入&quot;$on&quot;會顯示以字串&quot;on&quot;開頭的每個短語：

   &quot;**on** line banking和「**on**-line付款。」

* 鍵入&quot;on$&quot;會顯示以字串&quot;on&quot;結尾的每個片語：

   「銀牛」**on**&quot;和&quot;gold opti&quot;**on**.&quot;

* 鍵入&quot;on&quot;會顯示每個包含以字串&quot;on&quot;開頭的單詞的片語：

   &quot;**on**&#x200B;線上銀行和「銀行」 **on**&#x200B;線。」

* 輸入&quot;on&quot;會顯示每個包含以字串&quot;on&quot;結尾的字詞的片語：

   「布爾利」**on** coins和silver bulli **on**.&quot;

* 使用&quot;on&quot;會將包含字串&quot;on&quot;的每個片語顯示為字詞：

   &quot;**on** 線上銀行和「銀行」 **on** 線。」
