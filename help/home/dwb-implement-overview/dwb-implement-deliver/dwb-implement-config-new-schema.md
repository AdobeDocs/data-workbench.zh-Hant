---
description: 本檔案說明如何在新架構建立後變更所有預設資料工作台組態。
title: 新架構的配置更改
uuid: 7d59fc28-ce56-49e2-b068-d5e286dcc057
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 新架構的配置更改{#configuration-changes-for-new-schema}

本檔案說明如何在新方案生效後變更所有預設資料工作台組態。

## 瞭解資料集結構 {#section-2ffac5170c894781bc943565af7ad479}

資料集架構的基礎由構成資料工作台網頁分析架構骨幹的一組關鍵關係組成。 在下列範例中，一般的Web分析架構提供訪客、瀏覽和頁面檢視之間關係的概念。 ![](assets/dwb_impl_schema_change1.png)

* 任何特定訪客都可能有一或多次瀏覽。
* 任何指定的瀏覽都只由一位訪客產生。
* 任何特定瀏覽皆可能包含一或多個頁面檢視。
* 任何指定頁面檢視都只屬於一次瀏覽。 `<discoiqbr>`

隨著網路和商業世界的逐漸發展，網路和資料分析的需求也隨之改變。 網站一開始就是檢視內容的地方。 現在，您可以檢視內容；透過聊天、視訊或提交內容，以互動方式進行對應；購買產品；等等。 此外，企業現在希望將其Web資料與業務中其他資料通道整合，以更全面地瞭解其整體業務。 例如，企業可能想要將其網路、客服中心、電子郵件、社交網路、儲存和客戶資料整合在一起。 透過離線和線上通道的整合，資料集結構在沒有兩個資料集結構相同的年份中不斷演化。

`<discoiqbr>`當您整合線上和離線資料時，「訪客」一詞不一定適合。 因此，有時候會使用「customer」一詞來取代訪客。 ![](assets/dwb_impl_schema_change2.png) ![](assets/dwb_impl_schema_change3.png)

「參與」層級用於在您擁有來自多個資料來源的資料時啟用單一時間檢視。 例如，假設您只有單一資料來源：網站上訪客活動收集的電子商務資料。 在此情況下，「瀏覽」層級會指出這些訪客瀏覽您的網站。 請注意時間維度- 「日」、「周」、「月」等。 -通常在「瀏覽」層級擷取。

類似地，「事件」層級會將參與期間發生的所有事件（頁面檢視、呼叫中心等）帶入。 它結合了客戶參與期間的所有線上和線下活動。

## DWB中新的可數結構 {#section-b77638ec04e4441cb51c56fd3d4abeb6}

新的架構結構會取代「依客戶訪客」、「依參與瀏覽」和「依事件點擊」。 ![](assets/dwb_impl_schema_change4.png)

## 根據新資料集模式更改配置 {#section-27135515be5c471ba2ee879d1ef4771f}

若要將資料集結構從訪客變更為客戶，您必須變更下列設定檔案：

1. 定義可計數和擴展維的「資料集」資料夾下的所有配置檔案。 ![](assets/dwb_impl_schema_change5.png)

1. 「維度」檔案夾下的設定檔案，其中「訪客」、「瀏覽」或「事件」用作「層級」。

   範例：Campaign.cfg檔案。 在Adobe SC設定檔中，促銷活動是在瀏覽層級定義。 ![](assets/dwb_impl_schema_change6.png)

   下列範例提供從「瀏覽」到「參與」的父架構變更概念： ![](assets/dwb_impl_API10.png)

1. 由於有些量度是衍生或建立自可計數表，因此需要修改或建立「量度」檔案夾下的設定檔案。

   例如：建立新量度 [!DNL Customers.metric with formula = sum(one,customer)] 或作為頁面檢視。metric, *在點擊* 層級定義它。 修改量度，然後將層級變更為「事件」而非「點擊」。

   在點擊層級定義的Adobe SC頁面檢視度量： ![](assets/dwb_impl_API8.png)

   `<discoiqbr>` 以 `<discoiqbr>`下是依據新架構的「頁面檢視」度量： ![](assets/dwb_impl_API9.png)

1. 變更 *度量資料夾中的order.txt* ，以反映與客戶、參與和事件相關的新度量或修改度量。

   Adobe *SC order.txt檔* 。 ![](assets/dwb_impl_API11.png)

   *Order.txt* file with new schema changes: ![](assets/dwb_impl_API12.png)

1. 應將「視覺化」檔案夾下的所有設定檔案(.vw)變更為參照新層級：客戶、參與度和活動。 例如：2D流程圖、3D流程圖等

   2D程式地圖的Adobe SC預設URI.vw定義於點擊層級和瀏覽群組，如下所示： ![](assets/dwb_impl_API14.png)

   在URI.vw中為新模式所做的更改： ![](assets/dwb_impl_API15.png)

