---
description: 系統可以計算可計數維度的元素。
solution: Analytics
title: 可計數的維度
topic: Data workbench
uuid: 3312f5eb-69b9-43af-b32a-5c40e3050b29
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 可計數的維度{#countable-dimensions}

系統可以計算可計數維度的元素。

可計數維度通常用於建立總計度量，可傳回維度所有元素的計數或總計。 您可以定義可計數的維度，以計算例項，如訂房登記或產品訂單。 例如，您可以定義可計數的維度「訂單」，其元素（與您線上商店的訂單對應的記錄項目）可被計數。 如果您想在視覺化中顯示訂單計數，您可以定義「訂單」總和量度，此量度可評估維度或套用篩選器。

可計數維度可以是其他維度的父項，或是其他可計數維度的子項。

>[!NOTE]
>
>如果需要只提供某項計數的維，則應使用具有COUNT操作的數值維。 請參 [閱數值維度](../../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)。

可計數維度由下列參數定義：

<table id="table_9F3F093F5B074EA68CA4DCE731161F6C"> 
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
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於擴展維的注釋。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 輸入欄位有助於建立可計數維的條件。 如果指定，條件將限制維及其資料集模式中所有子代可見的日誌條目集。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 判斷維度是否出現在資料工作台介面中。 依預設，此參數會設為false。 例如，如果維度僅用作度量的基礎，您可以將此參數設為true，以隱藏資料工作台顯示的維度。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 金鑰 </td> 
   <td colname="col2"> <p>選填。用作鍵的欄位的名稱。 如果定義此參數，可計數維的元素對於可計數維父項的元素和指定為鍵的欄位的不同值的每個組合都存在。 </p> <p> 每個可計數維的元素都需要與一組連續的日誌條目相關。 因此，如果日誌條目未按鍵排序，則每次鍵欄位更改時都會建立可計數維的元素。 為避免此情況，Adobe建議您使用按時間順序連續的唯一金鑰。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父代 </td> 
   <td colname="col2"> <p>父維的名稱。 任何可計數的維度都可以是父項維度。 若要讓維度成為資料集結構中的頂層維度，請將參數設為"root"。 定義的維度會成為資料集的根可計數維度。 例如，如果您使用網站，「訪客」維度是您資料集的根可計數維度。 </p> <p> <p>注意： 雖然您的根可計數維度不必與資料中的追蹤ID相關聯，但Adobe建議您設定資料集的根可計數維度，以使用追蹤ID欄位(x-trackingid)作為其索引鍵。 因此，根可計數的每個元素都與x-trackingid的唯一值相關聯，而每個元素的所有資料都會分組在一起。 如果您想要以不同方式設定資料集，請聯絡Adobe。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例說明使用從網站流量收集的事件資料來定義可計數維度。 可計數的維度會計算指定作業中的Web促銷活動事件。 假設所有電子郵件促銷活動資源都是從網頁伺服器要求，而&quot;email=&quot;是cs-uri-query的一部分。 在此範例中，訪客在指定作業期間回應電子郵件促銷活動的次數是值得關注的，而非cs-uri-query(email)欄位的實際值。

![](assets/cfg_Transformation_Dim_Countable.png)

此範例也說明使用從網站流量收集的事件資料來定義可計數維度，但它有已定義的Key參數。 「會話」可計數維使用x-session-key欄位作為其鍵。 (x-session-key欄位是轉換的輸出， [!DNL Sessionize] 且每個作業都有唯一的值。)訪客維度（父項）的元素與x-session-key欄位的每個唯一組合都是「工作階段」維度的元素。

![](assets/cfg_Transformation_Dim_Countable2.png)

