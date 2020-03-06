---
description: 您可以自訂功能表的外觀，包括工作區視窗功能表（在任何工作區中按滑鼠右鍵即可存取）和功能表，其中列出度量、維度和對應圖層。
solution: Analytics
title: 自訂功能表
topic: Data workbench
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 自訂功能表{#customize-a-menu}

您可以自訂功能表的外觀，包括工作區視窗功能表（在任何工作區中按滑鼠右鍵即可存取）和功能表，其中列出度量、維度和對應圖層。

任何菜單的層次都反映了其目錄的結構 [!DNL Profile Manager]。 例如，工作區窗口菜單鏡像菜單目錄的結構，度量菜單鏡像度量目錄的結構。 對於任何菜單，對應的目錄可能包含以下項目：

* **檔案：** 這些檔案代表您可以按一下對應功能表項目來開啟的視覺化、圖例、註解、管理介面、量度、維度或地圖圖層。
* **檔[!DNL order.txt]案：** 此檔案會指定功能表顯示項目的順序。
* **子目錄：** 每個子目錄都表示一個子菜單。 每個子目錄可包含其自己的檔案、子目錄和 [!DNL order.txt] 檔案。

例如，功能表 [!DNL Add Legend] 會依此順序包含功能表項目「量度」、「顏色」、「值」和「可信度」。 相比之下，中的「菜單\添加圖例」 [!DNL Profile Manager] 目錄包含 [!DNL Color.vw][!DNL Confidence.vw]、 [!DNL Metric.vw]、和 [!DNL Value.vw][!DNL order.txt] 檔案（按字母順序排列），以及控制其他檔案順序的檔案。
