---
description: 指定輸出格式的准則。
title: 輸出格式
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
exl-id: e695eaf4-ebe5-4dd1-8191-8045021d6411
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# 輸出格式{#output-format}

指定輸出格式的准則。

* 每個量度或維度名稱必須以百分比符號(%)開始和結束。

   * %XYZ%指定與級別元素對應的維XYZ元素。 如果維XYZ不是一對一或一對多且級別為「級別」，則會生成錯誤。
   * %=XYZ%指定給定「級別」元素的量度或量度公式XYZ的值。

* Dimension名稱為兩個或兩個以上字詞，不需要下划線。
* 兩個或兩個以上字詞的量度名稱需要底線。

>[!NOTE]
>
>如果按住Ctrl鍵並在[!DNL Output Format]欄位中按一下滑鼠右鍵，則會出現[!DNL Insert menu]。 此功能表包含常用作分隔字元的特殊字元（例如Tab）清單。

如果您要匯出區段的作業持續時間資料，您必鬚根據「作業持續時間」度量建立新的度量。 此新度量僅用於區段匯出的[!DNL Output Format]欄位，讓Microsoft Excel可正確解譯持續時間少於1小時的作業。 若要建立新的作業持續時間度量，請開啟[!DNL Session Duration.metric]檔案（從[!DNL Profile Manager]），並將井號(#)插入ftime字串：[!DNL ftime = string: %#H:%M:%S]

井字型大小會將前導&quot;0&quot;附加至小於1小時的作業期間。 因此，Excel會將0:53:21解譯為53分21秒。 以不同名稱儲存新量度，並將其上傳至適合其他人使用的描述檔，方法是在[!DNL User]欄中按一下檔案的核取標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>*。
