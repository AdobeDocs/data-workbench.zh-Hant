---
description: 字串和數值參數分別作為其值字串和數字。
solution: Analytics
title: 字串與數值參數
topic: Data workbench
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 字串與數值參數{#string-and-numeric-parameters}

字串和數值參數分別作為其值字串和數字。

可以互換使用，但必須定義數值參數以具有數值。 在定義轉換、條件和擴展尺寸時，可以引用字串和數值參數，也可以在同一行中引用多個參數。

您無法在或欄位中參考字串和 [!DNL Input] 數值參 [!DNL Output] 數，但可以使用字串參數來定義常數輸入欄位。 此外，您無法在解碼器或解碼器群組中參考字串和數值參數。

此範例顯示定 [!DNL Log Processing Dataset Include] 義字串參數和數值參數的檔案。 請注意，名為&quot;Value Lookups&quot;的字串參數定義了相對於資料工作台伺服器安裝目錄的檔案位置(Lookups\Values)。

![](assets/cfg_Parameters_StringNumeric.png)

