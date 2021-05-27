---
description: 關於工作表運算式和使用儲存格參考的概念資訊。
title: 工作表運算式
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
exl-id: 1ff3ec24-0363-4b6c-8c91-31e49ed0f7c4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 2%

---

# 工作表運算式{#worksheet-expressions}

關於工作表運算式和使用儲存格參考的概念資訊。

以下工作表提供有關查看銀行網站聯機應用程式表單上提供的「應用程式嚮導」頁面的訪客的詳細資訊。

![](assets/client-wkst.png)

* 欄A顯示要評估的訪客類別清單：來自反向連結A的訪客、反向連結訪客和反向連結訪客。
* 欄B顯示每個類別中檢視了「立即套用」頁面的訪客人數。
* 欄C顯示同時檢視「立即套用」和「應用程式精靈」頁面的訪客。
* 欄D包含三個類別中同時檢視「應用程式精靈」頁面的「立即套用」檢視器的百分比。

工作表會顯示，檢視「立即套用」頁面的反向連結A所轉介的訪客中，約有55%已檢視「應用程式精靈」頁面。

下表提供上一個示例中工作表的示例公式：

<table id="table_0F5EFDB58040465AB599E6BE93324822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 工作表單元格 </th> 
   <th colname="col2" class="entry"> 公式 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>B2 </p> <p>檢視「立即套用」頁面的訪客 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>已檢視「立即套用」頁面的反向連結訪客 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>已檢視「立即套用」頁面的反向連結A的反向連結訪客 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"  </span> </p> <p> 和<span class="filepath">反向連結="參考A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>已檢視「立即套用」頁面和「應用程式精靈」頁面的訪客 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitors[Page="/applynow/default.asp"  </span> </p> <p> 和<span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>已瀏覽「立即應用」頁面和「應用程式精靈」頁面的反向連結訪客 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"  </span> </p> <p> 和<span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>已檢視「立即套用」頁面和「應用程式精靈」頁面的反向連結A的訪客 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"</span> </p> <p> 和<span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> 和<span class="filepath">反向連結="參考A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>檢視「立即套用」頁面和「應用程式精靈」頁面的訪客百分比 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>檢視「立即套用」頁面和「應用程式精靈」頁面的反向連結訪客百分比 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>檢視「立即套用」頁面和「應用程式精靈」頁面之反向連結A的反向連結訪客百分比 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

和其他視覺效果一樣，當您在工作區的其他視覺效果中進行選取時，工作表會自動更新。 有關進行選擇的詳細資訊，請參閱[在視覺效果中進行選擇](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746)。

在下列Web資料範例中，已在「依日的工作階段」視覺效果中選取數天的工作階段資料。 工作表顯示在選取的時間範圍內，檢視「立即套用」頁面的反向連結A訪客中，約有69%也檢視了「應用程式精靈」頁面。 若沒有此選取項目（如上例所示），大約55%的反向連結A的訪客檢視了「立即套用」頁面和「應用程式精靈」頁面。

![](assets/client-exp.png)

## 使用單元格引用{#section-0004e315c9c94d359b1a8a39794ba555}

您可以使用儲存格參考取代任何字串，不論字串本身或工作表中的其他運算式內。

* **簡單儲存格參考：** 儲存格A2包含文字「訪客」，此文字用於標題。單元格B2包含[!DNL eval(A1)]，其評估為[!DNL =Visitors]。

* **篩選儲存格參考：** 儲存格A5包含昨天的日期。儲存格B5包含[!DNL訪客[ Day=A5 ]]，會評估昨天的訪客數量。

* **串連的儲存格參考：** 儲存格A5包含今天的日期，而儲存格A6則包含08:00至08:59的一小時時段。儲存格B6包含[!DNL Visitors[ Hour=A5+&quot; &quot;+A6 ]]，其會評估今天上午8:00到上午9:00之間的訪客數量。
