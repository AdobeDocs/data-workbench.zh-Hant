---
description: 指定輸出格式的准則。
title: 輸出格式
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
exl-id: e695eaf4-ebe5-4dd1-8191-8045021d6411
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# 輸出格式{#output-format}

{{eol}}

指定輸出格式的准則。

* 每個量度或維度名稱的開頭和結尾都必須加上百分比符號(%)。

   * %XYZ%指定與級別元素對應的維XYZ的元素。 如果維度XYZ不是具有「等級」的一對一或一對多，則會產生錯誤。
   * %=XYZ%指定給「級別」元素的量度或量度公式XYZ的值。

* Dimension名稱為兩個或兩個以上字詞時不需要底線。
* 兩個或兩個以上的量度名稱需要底線。

>[!NOTE]
>
>按住Ctrl鍵，然後在 [!DNL Output Format] 欄位， [!DNL Insert menu] 框。 此菜單包含通常用作分隔符的特殊字元清單（如Tab）。

如果您想要匯出區段的工作階段期間資料，必鬚根據「工作階段期間」量度建立新量度。 新量度，僅供搭配 [!DNL Output Format] 欄位匯出，可讓Microsoft Excel正確解譯持續時間少於一小時的工作階段。 若要建立新的工作階段持續時間量度，請開啟 [!DNL Session Duration.metric] 檔案(從 [!DNL Profile Manager])，並將井字型大小(#)插入到ftime字串中： [!DNL ftime = string: %#H:%M:%S]

井字型大小會使前導的「0」附加至少於1小時的工作階段期間。 因此，Excel會解釋0:53:21分53分21秒。 以不同名稱儲存新量度，並以滑鼠右鍵按一下中檔案的核取記號，將其上傳至適當的設定檔供其他人使用 [!DNL User] 欄，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
