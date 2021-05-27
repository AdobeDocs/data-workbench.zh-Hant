---
description: 您可以自訂功能表的外觀，包括工作區視窗功能表（在任何工作區中按一下滑鼠右鍵即可存取）和列出量度、維度和映射圖層的功能表。
title: 自訂功能表
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# 自訂功能表{#customize-a-menu}

您可以自訂功能表的外觀，包括工作區視窗功能表（在任何工作區中按一下滑鼠右鍵即可存取）和列出量度、維度和映射圖層的功能表。

任何菜單的層次結構都反映了[!DNL Profile Manager]中其目錄的結構。 例如，工作區窗口菜單鏡像了菜單目錄的結構，度量菜單鏡像了度量目錄的結構。 對於任何菜單，相應的目錄可能包含以下項：

* **檔案：** 這些檔案代表視覺效果、圖例、註解、管理介面、量度、維度或地圖圖層，您可以按一下對應的功能表項目來開啟這些圖層。
* **檔 [!DNL order.txt] 案：** 此檔案會指定功能表顯示其項目的順序。
* **子目錄：** 每個子目錄代表子功能表。每個子目錄可包含其自己的檔案、子目錄和[!DNL order.txt]檔案。

例如，[!DNL Add Legend]功能表會依序包含功能表項目「量度」、「顏色」、「值」和「信賴度」。 相比之下，[!DNL Profile Manager]中的「菜單\添加圖例」目錄包含按字母順序排列的檔案[!DNL Color.vw]、[!DNL Confidence.vw]、[!DNL Metric.vw]和[!DNL Value.vw]，以及控制其他檔案順序的[!DNL order.txt]檔案。
