---
description: 工作表運算式和使用儲存格參考的概念性資訊。
title: 工作表運算式
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
exl-id: 1ff3ec24-0363-4b6c-8c91-31e49ed0f7c4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 2%

---

# 工作表運算式{#worksheet-expressions}

工作表運算式和使用儲存格參考的概念性資訊。

以下工作表提供有關瀏覽銀行網站線上應用程式表單上「應用程式精靈」頁面的訪客的詳細資訊。

![](assets/client-wkst.png)

* 欄A顯示要評估的訪客類別清單：訪客、反向連結訪客和反向連結A的反向連結訪客。
* 欄B顯示每個類別中檢視「立即套用」頁面的訪客數。
* 欄C顯示同時檢視「立即套用」和「應用程式精靈」頁面的訪客。
* 欄D包含三個類別中「立即套用」檢視器的百分比，這些類別也檢視了「應用程式精靈」頁面。

工作表顯示，從「反向連結A」檢視「立即套用」頁面的訪客中，約有55%的訪客也檢視了「應用程式精靈」頁面。

下表提供了上例中工作表的示例公式：

<table id="table_0F5EFDB58040465AB599E6BE93324822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 工作表儲存格 </th> 
   <th colname="col2" class="entry"> 公式 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>B2 </p> <p>檢視「立即套用」頁面的訪客 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =訪客[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>已參考檢視「立即套用」頁面的訪客 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>來自已檢視「立即套用」頁面之反向連結A的反向連結訪客 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"  </span> </p> <p> AND <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>檢視「立即套用」頁面和「應用程式精靈」頁面的訪客 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitors[Page="/applynow/default.asp"  </span> </p> <p> 和<span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>已參考檢視「立即套用」頁面和「應用程式精靈」頁面的訪客 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"  </span> </p> <p> 和<span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>從「反向連結A」反向連結，檢視「立即套用」頁面和「應用程式精靈」頁面的反向連結訪客 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"</span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> AND <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
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
   <td colname="col1"> <p>D4 </p> <p>來自反向連結A的反向連結訪客檢視「立即套用」頁面和「應用程式精靈」頁面的百分比 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

和其他視覺化一樣，當您在工作區中的其他視覺化中進行選取時，工作表會自動更新。 有關選擇的詳細資訊，請參閱[在視覺化中選擇](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746)。

在下列Web資料範例中，已在「依日的作業」視覺化中選取數天的作業資料。 工作表顯示，在選取的時間範圍內，約有69%來自反向連結A且檢視「立即套用」頁面的訪客也檢視了「應用程式精靈」頁面。 若未選取此選項（如上例所示），大約55%來自反向連結A的訪客檢視了「立即套用」頁面和「應用程式精靈」頁面。

![](assets/client-exp.png)

## 使用單元格引用{#section-0004e315c9c94d359b1a8a39794ba555}

您可以使用儲存格參考來取代任何字串，不論是單獨使用或在工作表中的其他運算式內。

* **簡單儲存格參** 考：儲存格A2包含用作標題的「訪客」文字。單元格B2包含[!DNL eval(A1)]，評估為[!DNL =Visitors]。

* **篩選儲存格參考：** 儲存格A5包含昨天的日期。儲存格B5包含[!DNL訪客[ Day=A5 ]]，其評估為昨天的訪客數。

* **串連的儲存格參考：** 儲存格A5包含今天的日期，而儲存格A6包含08:00至08:59的一小時時段。儲存格B6包含[!DNL訪客[小時=A5+&quot;+A6 ]]，其評估為今天上午8:00至上午9:00之間的訪客數。
