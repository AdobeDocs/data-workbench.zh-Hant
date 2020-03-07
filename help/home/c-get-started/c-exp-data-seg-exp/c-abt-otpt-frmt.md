---
description: 指定輸出格式的准則。
solution: Analytics
title: 輸出格式
topic: Data workbench
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 輸出格式{#output-format}

指定輸出格式的准則。

* 每個量度或維度名稱必須以百分比符號(%)開始和結束。

   * %XYZ%指定與級別元素對應的維XYZ元素。 如果維XYZ不是一對一或一對多且級別為「級別」，則會生成錯誤。
   * %=XYZ%指定給定「級別」元素的量度或量度公式XYZ的值。

* 兩個或兩個以上字詞的維名稱不需要下划線。
* 兩個或兩個以上字詞的量度名稱需要底線。

>[!NOTE]
>
>如果按住Ctrl鍵並在欄位中按一下滑鼠右鍵， [!DNL Output Format] 則會出現 [!DNL Insert menu] 畫面。 此功能表包含常用作分隔字元的特殊字元（例如Tab）清單。

如果您要匯出區段的作業持續時間資料，您必鬚根據「作業持續時間」度量建立新的度量。 此新量度僅用於區段匯出欄 [!DNL Output Format] 位，讓Microsoft Excel可正確解譯持續時間少於一小時的作業。 若要建立新的作業持續時間度量，請 [!DNL Session Duration.metric] 開啟檔案(從 [!DNL Profile Manager])，並將井號(#)插入ftime字串： [!DNL ftime = string: %#H:%M:%S]

井字型大小會將前導&quot;0&quot;附加至小於1小時的作業期間。 因此，Excel會將0:53:21解譯為53分21秒。 以不同名稱儲存新量度，並將其上傳至適當的描述檔，方法是在欄中按一下該檔案的核取標籤，然後按一 [!DNL User] 下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。
