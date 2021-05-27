---
description: 字串和數值參數分別作為其值字串和數字。
title: 字串與數值參數
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
exl-id: 37d004da-cde7-4b67-b0cb-0acbb6d8ad68
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 5%

---

# 字串與數值參數{#string-and-numeric-parameters}

字串和數值參數分別作為其值字串和數字。

您可以交互使用，但必須定義數值參數以具有數值。 在定義轉換、條件和擴展維時，可以參考字串和數值參數，並且可以在同一行中引用多個參數。

不能在[!DNL Input]或[!DNL Output]欄位中引用字串和數值參數，但可以使用字串參數定義常數輸入欄位。 此外，您無法在解碼器或解碼器群組中參考字串和數值參數。

此示例顯示一個[!DNL Log Processing Dataset Include]檔案，該檔案定義字串參數和數值參數。 請注意，名為「值代碼」的字串參數會定義相對於Data Workbench伺服器安裝目錄的檔案位置(Lookups\Values)。

![](assets/cfg_Parameters_StringNumeric.png)
