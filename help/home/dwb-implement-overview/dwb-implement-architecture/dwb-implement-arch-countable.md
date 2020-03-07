---
description: 資料工作台(DWB)中用於設計和實施方案的可計數表的說明。
title: 架構設計可計數結構
uuid: 2530980d-1c6b-4a96-b9c1-431fc75678bb
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# 架構設計可計數結構{#schema-design-countable-structures}

資料工作台(DWB)中用於設計和實施方案的可計數表的說明。

## 瞭解資料工作台中的可計數 {#section-6e6b8d1c17634d669e62c91a80a0bc62}

最高層是可計數的維度。 可計數的維度提供兩個主要功能。 首先，它們是您要計算其元素的維度。 換言之，可計數器可回答以下問題：

* 有多少訪客瀏覽了您的首頁？

* 來自Google.com的瀏覽次數為何？

`<discoiqbr>`可計數維度通常用於建立總計度量，可傳回維度所有元素的計數或總計。 您可以定義可計數的維度，以計算例項，如訂房登記或產品訂單。 例如，您可以定義可計數的維度訂單，其元素（與線上商店的訂單對應的記錄項目）可被計數。 如果您想在視覺化中顯示訂單計數，您可以定義訂單總和量度，此量度可以透過維度進行評估，或套用篩選器。

可計數維度可以是其他維度的父項，或是其他可計數維度的子項。

雖然您的根可計數維度不必與資料中的追蹤ID相關聯，但Adobe建議您設定資料集的根可計數維度，使用追蹤ID欄位(x-trackingid)作為索引鍵。 因此，根可計數的每個元素都與x-trackingid的唯一值相關聯，而每個元素的所有資料都會分組在一起。

可計數維度由下列參數定義：

<table id="table_5E00B72CFDD645368ADCC25AB9B5E53D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設值 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 資料工作台中使用者所看見之維度的描述性名稱。 維度名稱不能包含連字型大小(-)。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>意見 </p> </td> 
   <td colname="col2"> <p>選填。關於擴展維的注釋。

    &lt;/p> &lt;/td>
<td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>條件 </p> </td> 
   <td colname="col2"> <p>輸入欄位有助於建立可計數維的條件。 如果指定，條件將限制維及其資料集模式中所有子代可見的日誌條目集。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 判斷維度是否出現在資料工作台介面中。 依預設，此參數會設為false。 例如，如果維度僅用作度量的基礎，您可以將此參數設為true，以隱藏資料工作台顯示的維度。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 金鑰 </td> 
   <td colname="col2"> <p>選填。用作鍵的欄位的名稱。 如果定義此參數，可計數維的元素對於可計數維父項的元素和指定為鍵的欄位的不同值的每個組合都存在。 </p> <p>每個可計數維的元素都需要與一組連續的日誌條目相關。 因此，如果日誌條目未按鍵排序，則每次鍵欄位更改時都會建立可計數維的元素。 為避免此情況，Adobe建議您使用按時間順序連續的唯一金鑰。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父代 </td> 
   <td colname="col2"> <p> 父維的名稱。 任何可計數的維度都可以是父項維度。 若要讓維度成為資料集結構中的頂層維度，請將參數設為"root"。 定義的維度會成為資料集的根可計數維度。 例如，如果您使用網站，「訪客」維度是您資料集的根可計數維度。 </p> <p>注意：雖然您的根可計數維度不必與資料中的追蹤ID相關聯，但Adobe建議您設定資料集的根可計數維度，以使用追蹤ID欄位(x-trackingid)作為其索引鍵。 因此，根可計數的每個元素都與x-trackingid的唯一值相關聯，而每個元素的所有資料都會分組在一起。 如果您想要以不同方式設定資料集，請聯絡Adobe。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例說明使用從網站流量收集的事件資料來定義可計數維度。 可計數的維度會計算指定作業中的Web促銷活動事件。 假設所有電子郵件促銷活動資源都是從網頁伺服器要求，而&quot;email=&quot;是cs-uri-query的一部分。 在此範例中，訪客在指定作業期間回應電子郵件促銷活動的次數是值得關注的，而非cs-uri-query(email)欄位的實際值。

![](assets/dwb_impl_arch_1.png)

可計數表的第二個主要功能是它們構成了資料集模式結構的骨幹。 您的資料結構和所有其他維度會組織成群組在下方，且屬於可計數的。 換言之，如果我們將維度視為「類別」，則可計數是我們將這些「類別」組織成群組的方式。
當維度分組在可計數維度下時，這些維度據說位於可計數維度的「層級」。 例如，在下圖中，您可以看到「電子郵件位址」位於訪客層級，「瀏覽器」位於瀏覽層級。 「父項」和「子項」是指可計數與其下方分組的維度之間的關係。 例如，訪客是電子郵件地址的「父」。 相反地，電子郵件地址是訪客的「子系」。 ![](assets/dwb_impl_arch_2.png) ![](assets/dwb_impl_arch_3.png)

## 在資料工作台中建立可計數 {#section-491f3e8e4fbc429e95d6c97f012a208e}

執行下列步驟以在資料工作台中建立可計數：

1. 開啟描述檔管理員
1. 在「轉換」資料夾下，建立配置檔案並在工作站中將其開啟。
1. 在「延伸維度」下方，按一下滑鼠右鍵並選擇「新增->可計數」，如下所示： ![](assets/dwb_impl_arch_4.png)

1. 輸入新可計數的名稱。 在下例中，定義了客戶可計數。 如果它是「最高級別可計數」，則位於「父寫入根」中。 ![](assets/dwb_impl_arch_5.png)

   如果「可計數」不是頂層1，則在父欄位中提供「父可計數」的名稱。 在以下範例中，會建立「參與計數」，此計數的父代為「客戶」。 ![](assets/dwb_impl_arch_5.png)

如需有關架構設計、可計數結構及離線資料饋送設定的資料工作台架構詳細資訊，請參閱資料集架構介面 [](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-dtst-sch-intrf.html) 與維度與度量參考 [](../../assets/insight_sc_implementation.pdf)。
