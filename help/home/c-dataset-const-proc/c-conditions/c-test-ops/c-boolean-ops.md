---
description: 布爾運算結合測試運算的結果，其功能為布爾運算的子項。
solution: Analytics
title: 布林運算
topic: Data workbench
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 布林運算{#boolean-operations}

布爾運算結合測試運算的結果，其功能為布爾運算的子項。

有關測試操作的資訊，請參 [閱測試操作](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144)。 在定義工序 [!DNL boolean] 時，可以為工序定義零個或多個子項。

**要將子條件添加到布爾操作，請執行以下操作：**

1. 按一下右鍵與操作對應的名稱或編 [!DNL Boolean] 號。
1. 按一 **[!UICONTROL Add new child]** 下並選擇要新增的可用條件類型。
1. 重複步驟1和2，直到您為操作添加了所有所需的子條 [!DNL Boolean] 件。

   >[!NOTE]
   >
   >按一下右鍵與操作對應的名稱或編號時， [!DNL Boolean] 會看到菜單 [!DNL Add new sibling] 選項。 同級是條件層次結構中與按一下右鍵的操作處於相同相對位置 [!DNL Boolean] 的另一個條件。 為操作添加新同級 [!DNL Boolean] 與通過按一下右鍵或參數添加新條件 [!DNL Condition] 相 [!DNL Log Entry Condition] 同。

**要從布爾運算中刪除子條件，請執行以下操作：**

1. 按一下右鍵子條件的名稱或與要從操作中刪除的子條件相對應的編 [!DNL Boolean] 號。
1. 按一下 **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***> ，其中number是與要刪除的子條件對應的數字。

本節討論以下條件：

* [和](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [兩者皆不](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [或](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## 和 {#section-a14dba4b07cc4ab9aeb20868f773db7c}

該條 [!DNL And] 件可以有零個或更多子條件，並且當其子節點無返回false時返回true。

該條 [!DNL And] 件構成資料工作台伺服器內所有條件測試的根操作。 如果條 [!DNL And] 件不含子項，則條件會評估為true，而相關的作業會繼續進行。 這就是為什麼只有條件測試 [!DNL And] 的操作始終會執行，以及它用作所有條件測試的根的原因。

此示例說明如 [!DNL And] 何使用條件來確保在 [!DNL Copy] 2006年只發生日誌條目的日期和請求的頁面時都發生轉換 [!DNL /products/purchase.asp]。

![](assets/cfg_Condition_AndCondition.png)

## Neither {#section-7e48b61266aa43ecbc48b979bf5e939b}

條 [!DNL Neither] 件可以有零個或多個子條件，如果其任何子條件評估為true，則返回false。 如果條 [!DNL Neither] 件不含子項，則其子項無法傳回true。 結果，條件 [!DNL Neither] 評估為true。

以下示例顯示一個 [!DNL Neither] 條件，其子 [!DNL Range] 項為兩個條件。 如定義，此條 [!DNL Neither] 件排除在2007年1月1日和2007年1月10日之間或在2007年1月12日到2007年1月14日期間發生的日誌條目。 此條件可用來在收集的 [!DNL Log Entry Condition] 資料有已知問題的期間，從資料集中消除交易。

![](assets/cfg_Condition_NeitherCondition.png)

## 或 {#section-a3aa0f56b6234f2680fa81939228326b}

條 [!DNL Or] 件可以有零個或多個子條件，並且如果其至少一個子條件評估為true，則返回true。 如果條 [!DNL Or] 件不含子項，則其子項無法傳回true。 結果，條件 [!DNL Or] 評估為false。

此示例顯示 [!DNL Or] 條件和條 [!DNL String Match] 件作為 [!DNL Range] 其子項的條件。 僅當 [!DNL Or][!DNL x-hasproblem] 日誌條目的值設定為yes或日誌條目在2007年1月1日到2007年1月10日的時間範圍內發生時，才滿足此條件。

![](assets/cfg_Condition_OrCondition.png)

