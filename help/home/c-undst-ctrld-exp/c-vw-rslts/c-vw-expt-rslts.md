---
description: 在將新欄位添加到Log Processing.cfg並建立了新的拆分轉換和擴展維後，您可以在資料重新處理的快速輸入階段完成後立即查看所建立的新擴展維。
solution: Analytics
title: 檢視實驗結果
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
exl-id: cada693c-79cb-4f49-a2f0-6ff60425be1c
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---

# 檢視實驗結果{#viewing-the-experiment-results}

在將新欄位添加到Log Processing.cfg並建立了新的拆分轉換和擴展維後，您可以在資料重新處理的快速輸入階段完成後立即查看所建立的新擴展維。

預設情況下，此維顯示每個實驗組的會話數。

**查看實驗尺寸**

* 在 [!DNL Insight]，開啟包含您建立的實驗尺寸的表。

   表示當前運行的每個實驗以及每個實驗內的每個組的實驗尺寸元素顯示為每個組的當前會話數。 每個組都使用實驗名稱后跟組名稱的下列格式命名：

   *實驗名稱。組名稱*

   例如︰[!DNL New Homepage.Control]

下表顯示了在中建立的「受控實驗組」維 [!DNL Transformation.cfg] 以及每個實驗和小組。

新首頁實驗顯示在表的底部，其兩組：控制項和索引2。

![](assets/controlledexpgrps.png)

現在，您可以使用實驗尺寸和任何相關度量來探索和解釋實驗結果，並建立詳細描述這些結果的有用報告。
