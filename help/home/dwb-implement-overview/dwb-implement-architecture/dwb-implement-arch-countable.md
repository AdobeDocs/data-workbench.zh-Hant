---
description: Dataworkbench(DWB)中用於設計和實作結構的可數表說明。
title: 結構設計可數架構
uuid: 2530980d-1c6b-4a96-b9c1-431fc75678bb
exl-id: 4f2a2f8a-7b42-42bb-8ba1-2675ffe6b2c2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 3%

---

# 結構設計可數架構{#schema-design-countable-structures}

{{eol}}

Dataworkbench(DWB)中用於設計和實作結構的可數表說明。

## 了解Data Workbench中的可數 {#section-6e6b8d1c17634d669e62c91a80a0bc62}

最高層級是可數維度。 可數維度提供兩個主要函式。 首先，這些維度是您想要計算的元素。 換句話說，可數可回答以下問題：

* 有多少訪客瀏覽了您的首頁？

* 來自Google.com的瀏覽數？

`<discoiqbr>`可數維度通常用來建立總和量度，以傳回維度所有元素的計數或總和。 您可以定義可數維度，以計算例項，例如訂房預訂或產品訂單。 例如，您可以定義可數維度訂單，其元素（與線上商店訂單對應的記錄項目）可被計算。 如果您想在視覺效果中顯示訂單計數，可定義訂單總和量度，此量度可透過維度評估或套用篩選器。

可計數維度可以是其他維度的父項，或是其他可計數維度的子項。

雖然您的根可數維度不必與資料中的追蹤ID相關聯，但Adobe建議您設定資料集的根可數維度，使用追蹤ID欄位(x-trackingid)作為索引鍵。 因此，根可數的每個元素都與x-trackingid的唯一值相關聯，而每個元素的所有資料都會分組在一起。

可數維度由下列參數定義：

<table id="table_5E00B72CFDD645368ADCC25AB9B5E53D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> Data Workbench中使用者看到的維度描述性名稱。 維度名稱不能包含連字型大小(-)。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>註解 </p> </td> 
   <td colname="col2"> <p>選填。延伸維度的相關附註。

    &lt;/p> &lt;/td>
<td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>條件 </p> </td> 
   <td colname="col2"> <p>輸入欄位有助於建立可數維度的條件。 若已指定，條件會限制維度所可見的記錄項目集，以及資料集結構中其所有子項。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 判斷維度是否顯示在Data Workbench介面中。 此參數預設會設為false。 例如，如果維度僅作為量度的基礎，您可以將此參數設為true，以便在Data Workbench顯示中隱藏維度。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 金鑰 </td> 
   <td colname="col2"> <p>選填。要作為索引鍵的欄位名稱。 如果您定義此參數，可數維度的父元素與指定為索引鍵之欄位的不同值的每種組合，都會存在可數維度的元素。 </p> <p>可數維度的每個元素都需要與一組連續的記錄項目相關。 因此，如果日誌條目不是按鍵排序的，則每次鍵欄位更改時都會建立可數維的元素。 為避免此情況，Adobe建議您使用按時間順序連續的唯一金鑰。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父級 </td> 
   <td colname="col2"> <p> 父維的名稱。 任何可計數維度都可以是父維度。 若要將維度設為資料集結構中的頂層維度，請將參數設為「root」。 定義的維度會成為資料集的根可數維度。 例如，如果您使用的是網站，訪客維度是資料集的根可數維度。 </p> <p>注意：雖然您的根可數維度不必與資料中的追蹤ID相關聯，但Adobe建議您設定資料集的根可數維度，以使用追蹤ID欄位(x-trackingid)作為其索引鍵。 因此，根可數的每個元素都與x-trackingid的唯一值相關聯，而每個元素的所有資料都會分組在一起。 如果您想要以不同方式設定資料集，請聯絡Adobe。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例說明可數維度的定義，使用從網站流量收集的事件資料。 可數維度會計算指定工作階段內的Web促銷活動事件。 假設是，所有電子郵件促銷活動資源都是從Web伺服器請求，而cs-uri-query中包含&quot;email=&quot;。 在此範例中，訪客在指定工作階段期間回應電子郵件促銷活動的次數很受關注，而非cs-uri-query(email)欄位的實際值。

![](assets/dwb_impl_arch_1.png)

可數的第二項主要功能是，它們構成資料集結構的骨幹。 您的資料結構和所有其他維度會組織成分組，並屬於可數。 換句話說，如果將維度視為「類別」，則可數是將這些「類別」組織成群組的方式。
將維度分組在可數維度下時，會說明維度位於可數維度的「層級」。 例如，在下圖中，您會看到「電子郵件地址」位於訪客層級，而「瀏覽器」位於瀏覽層級。 「父項」和「子項」是指可數與其下分組的維度之間的關係。 例如，訪客是電子郵件地址的「父項」。 相反地，電子郵件地址是訪客的「子項」。 ![](assets/dwb_impl_arch_2.png) ![](assets/dwb_impl_arch_3.png)

## 在Data Workbench中建立可數 {#section-491f3e8e4fbc429e95d6c97f012a208e}

執行下列步驟以在Dataworkbench中建立可數：

1. 開啟設定檔管理員
1. 在轉換資料夾下，建立設定檔案並在工作站中開啟。
1. 在「延伸Dimension」下，按一下滑鼠右鍵並選擇「新增 — >可數」，如下所示： ![](assets/dwb_impl_arch_4.png)

1. 輸入新可數的名稱。 在以下範例中，已定義客戶可數。 如果它是最高級別可數，則在父寫入根中。 ![](assets/dwb_impl_arch_5.png)

   如果可數不是頂層可數，則在父欄位中提供父可數的名稱。 在以下範例中，會建立「參與可數」，且此可數的父項為「客戶」。 ![](assets/dwb_impl_arch_5.png)

如需結構設計、可數結構和離線資料饋送設定的Data Workbench架構詳細資訊，請參閱 [資料集結構介面](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-dtst-sch-intrf.html).
