---
description: 您可以自訂功能表的外觀，包括工作區視窗功能表（在任何工作區中按滑鼠右鍵即可存取）和功能表，其中列出度量、維度和對應圖層。
title: 自訂功能表
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# 自訂功能表{#customize-a-menu}

您可以自訂功能表的外觀，包括工作區視窗功能表（在任何工作區中按滑鼠右鍵即可存取）和功能表，其中列出度量、維度和對應圖層。

任何菜單的層次都反映了[!DNL Profile Manager]中其目錄的結構。 例如，工作區窗口菜單鏡像菜單目錄的結構，度量菜單鏡像度量目錄的結構。 對於任何菜單，對應的目錄可能包含以下項目：

* **檔案：這** 些檔案代表視覺化、圖例、註解、管理介面、量度、維度或映射圖層，您可以按一下對應的功能表項目來開啟。
* **檔 [!DNL order.txt] 案：** 此檔案指定功能表顯示項目的順序。
* **子目錄：每** 個子目錄代表一個子菜單。每個子目錄可包含其自己的檔案、子目錄和[!DNL order.txt]檔案。

例如，[!DNL Add Legend]功能表依此順序包含功能表項目「量度」、「顏色」、「值」和「可信度」。 相比之下，[!DNL Profile Manager]中的「菜單\添加圖例」目錄包含按字母順序排列的檔案[!DNL Color.vw]、[!DNL Confidence.vw]、[!DNL Metric.vw]和[!DNL Value.vw]，以及控制其他檔案順序的[!DNL order.txt]檔案。
