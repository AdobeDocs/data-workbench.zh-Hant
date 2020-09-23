---
description: 將新欄位新增至Log Processing.cfg並建立新的分割變形和延伸維度後，您就可以檢視在資料重新處理的快速輸入階段完成後建立的新延伸維度。
solution: Analytics,Analytics
title: 檢視實驗結果
topic: Data workbench
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---


# 檢視實驗結果{#viewing-the-experiment-results}

將新欄位新增至Log Processing.cfg並建立新的分割變形和延伸維度後，您就可以檢視在資料重新處理的快速輸入階段完成後建立的新延伸維度。

依預設，此維度會顯示每個實驗群組的作業數。

**若要檢視實驗尺寸**

* 在中的任何工 [!DNL Insight]作區中，開啟包含您建立的實驗維的表。

   實驗維度元素代表您目前執行的每個實驗以及每個實驗中的每個群組，顯示每個群組的目前作業數。 每個群組都會使用實驗名稱后接群組名稱，以下列格式命名：

   *實驗名稱。群組名稱*

   例如︰[!DNL New Homepage.Control]

下表顯示了在中建立的「受控實驗組」(Controlled Experity Groups) [!DNL Transformation.cfg] 尺寸以及每個實驗及其組。

「新首頁」實驗顯示在表格底部，其兩組：控制項和索引2.

![](assets/controlledexpgrps.png)

您現在可以使用實驗維度和任何相關度量來探索和解讀實驗結果，並建立詳細說明這些結果的有用報表。
