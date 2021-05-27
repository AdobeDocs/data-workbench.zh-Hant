---
description: 將新欄位新增至Log Processing.cfg並建立新的Split轉換和延伸維度後，您就可以在資料重新處理的「快速輸入」階段完成後，立即檢視所建立的新延伸維度。
solution: Analytics,Analytics
title: 檢視實驗結果
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
exl-id: cada693c-79cb-4f49-a2f0-6ff60425be1c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---

# 檢視實驗結果{#viewing-the-experiment-results}

將新欄位新增至Log Processing.cfg並建立新的Split轉換和延伸維度後，您就可以在資料重新處理的「快速輸入」階段完成後，立即檢視所建立的新延伸維度。

依預設，此維度會顯示每個實驗群組的工作階段數。

**若要檢視實驗維度**

* 在[!DNL Insight]中的任何工作區內，開啟含有您建立的實驗維度的表格。

   實驗維度元素代表您目前執行的每個實驗，以及每個實驗內的每個群組，會以每個群組目前的工作階段數顯示。 每個群組的命名格式如下，使用實驗名稱，後接群組名稱：

   *實驗名稱。組名稱*

   例如︰[!DNL New Homepage.Control]

下表顯示在[!DNL Transformation.cfg]中建立的受控實驗組維度以及每個實驗及其組。

新首頁實驗會顯示在表格底部，並包含其兩組：控制項和索引2。

![](assets/controlledexpgrps.png)

您現在可以使用實驗維度和任何相關量度來探索和解讀實驗結果，並建立詳細說明這些結果的有用報表。
