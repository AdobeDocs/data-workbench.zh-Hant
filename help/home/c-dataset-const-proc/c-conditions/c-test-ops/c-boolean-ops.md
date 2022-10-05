---
description: 布爾運算組合測試運算的結果，其作為布爾運算的子項。
title: 布林運算
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# 布林運算{#boolean-operations}

{{eol}}

布爾運算組合測試運算的結果，其作為布爾運算的子項。

有關測試操作的資訊，請參見 [測試操作](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). 當您定義 [!DNL boolean] 操作，您可以為操作定義零個或多個子項。

**將子條件添加到布林操作**

1. 以滑鼠右鍵按一下與 [!DNL Boolean] 操作。
1. 按一下 **[!UICONTROL Add new child]** 並選擇要添加的可用條件類型之一。
1. 重複步驟1和2，直到您已將所有所需的子條件新增至 [!DNL Boolean] 操作。

   >[!NOTE]
   >
   >當您以滑鼠右鍵按一下 [!DNL Boolean] 操作，你看 [!DNL Add new sibling] 的上界。 同級是條件階層中與 [!DNL Boolean] 按一下右鍵的操作。 為 [!DNL Boolean] 操作等同於以滑鼠右鍵按一下 [!DNL Condition] 或 [!DNL Log Entry Condition] 參數。

**要從布林操作中刪除子條件：**

1. 按一下右鍵子條件的名稱或與要從中刪除的子條件相對應的編號 [!DNL Boolean] 操作。
1. 按一下 **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>，其中number是與您要移除的子條件相對應的數字。

本節探討下列條件：

* [和](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [兩者皆不](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [或](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## 和 {#section-a14dba4b07cc4ab9aeb20868f773db7c}

此 [!DNL And] 條件可以有零個或多個子條件，且當其子節點未傳回false時傳回true。

此 [!DNL And] 條件會在data workbench伺服器內形成所有條件測試的根操作。 若 [!DNL And] 條件不包含子項，條件會評估為true，並執行相關的操作。 這就是為什麼只有 [!DNL And] 條件，因為條件測試一律會執行，以及為何將其用作所有條件測試的根。

此範例說明 [!DNL And] 條件用來確認 [!DNL Copy] 只有在2006年發生日誌條目的日期和請求的頁面都發生轉換時 [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## 兩者皆不 {#section-7e48b61266aa43ecbc48b979bf5e939b}

此 [!DNL Neither] 條件可以有零個或多個子條件，如果其任何子條件評估為true，則返回false。 若 [!DNL Neither] 條件不包含子項，其子項無法傳回true。 因此， [!DNL Neither] 條件會評估為true。

下列範例顯示 [!DNL Neither] 條件為兩 [!DNL Range] 孩子的條件。 如定義， [!DNL Neither] 條件不包括2007年1月1日至2007年1月10日之間或2007年1月12日至2007年1月14日期間發生的日誌條目。 此類條件可作為 [!DNL Log Entry Condition] 在已收集資料有已知問題的期間，從資料集中清除交易。

![](assets/cfg_Condition_NeitherCondition.png)

## 或 {#section-a3aa0f56b6234f2680fa81939228326b}

此 [!DNL Or] 條件可以有零個或多個子條件，並且如果其至少一個子條件評估為true，則返回true。 若 [!DNL Or] 條件不包含子項，其子項無法傳回true。 因此， [!DNL Or] 條件評估為false。

此範例顯示 [!DNL Or] 條件 [!DNL String Match] 條件和 [!DNL Range] 作為其子項的條件。 此 [!DNL Or] 只有在記錄項目具有 [!DNL x-hasproblem] 值設為yes或記錄項目發生在2007年1月1日到2007年1月10日的時間範圍內。

![](assets/cfg_Condition_OrCondition.png)
