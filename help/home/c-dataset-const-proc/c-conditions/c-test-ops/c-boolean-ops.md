---
description: 布爾運算組合測試運算的結果，其作為布爾運算的子項。
title: 布林運算
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# 布林運算{#boolean-operations}

布爾運算組合測試運算的結果，其作為布爾運算的子項。

有關測試操作的資訊，請參閱[測試操作](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144)。 定義[!DNL boolean]操作時，可以為該操作定義零個或多個子項。

**將子條件添加到布林操作**

1. 按一下右鍵與[!DNL Boolean]操作對應的名稱或編號。
1. 按一下&#x200B;**[!UICONTROL Add new child]**&#x200B;並選擇要添加的可用條件類型之一。
1. 重複步驟1和2，直到您為[!DNL Boolean]操作添加了所有所需的子條件。

   >[!NOTE]
   >
   >按一下右鍵與[!DNL Boolean]操作對應的名稱或數字時，您會看到[!DNL Add new sibling]菜單選項。 同級是條件層次結構中與按一下右鍵的[!DNL Boolean]操作相同的相對位置的另一個條件。 為[!DNL Boolean]操作添加新同級項與通過按一下右鍵[!DNL Condition]或[!DNL Log Entry Condition]參數添加新條件相同。

**要從布林操作中刪除子條件：**

1. 按一下右鍵要從[!DNL Boolean]操作中刪除的子條件的名稱或與子條件對應的編號。
1. 按一下&#x200B;**[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>，其中number是與要刪除的子條件相對應的數字。

本節探討下列條件：

* [和](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [兩者皆不](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [或](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## 和 {#section-a14dba4b07cc4ab9aeb20868f773db7c}

[!DNL And]條件可以具有零個或多個子條件，並且當其子節點未返回false時返回true。

[!DNL And]條件構成Data Workbench伺服器內所有條件測試的根操作。 如果[!DNL And]條件不含子項，則條件評估為true，並繼續相關操作。 這就是為什麼只有[!DNL And]條件作為條件測試的動作一律會執行，以及為什麼所有條件測試都使用它作為根。

此示例說明如何使用[!DNL And]條件確保在2006年只發生日誌條目的日期且請求的頁面為[!DNL /products/purchase.asp]時發生[!DNL Copy]轉換。

![](assets/cfg_Condition_AndCondition.png)

## 既不{#section-7e48b61266aa43ecbc48b979bf5e939b}

如果[!DNL Neither]條件的任何子條件評估為true，則條件可以具有零個或多個子條件並返回false。 如果[!DNL Neither]條件不包含子項，則其子項不能返回true。 因此，[!DNL Neither]條件會評估為true。

下列範例顯示[!DNL Neither]條件，其子項為兩個[!DNL Range]條件。 根據定義，[!DNL Neither]條件不包括2007年1月1日至2007年1月10日之間或2007年1月12日至2007年1月14日期間發生的日誌條目。 此類條件可作為[!DNL Log Entry Condition]使用，以在收集的資料有已知問題的期間，從資料集中消除交易。

![](assets/cfg_Condition_NeitherCondition.png)

## 或 {#section-a3aa0f56b6234f2680fa81939228326b}

[!DNL Or]條件可以具有零個或多個子條件，並且如果其至少一個子條件評估為true，則返回true。 如果[!DNL Or]條件不包含子項，則其子項不能返回true。 因此，[!DNL Or]條件會評估為false。

此示例顯示以[!DNL String Match]條件和[!DNL Range]條件作為子項的[!DNL Or]條件。 只有在日誌條目的[!DNL x-hasproblem]值設定為yes或日誌條目在2007年1月1日到2007年1月10日的時間範圍內發生時，才滿足[!DNL Or]條件。

![](assets/cfg_Condition_OrCondition.png)
