---
description: 測試結果必須清晰且有意義，讓您有信心根據這些結果做出重大決策。
solution: Insight,Analytics
title: 我該測試什麼？
topic: Data workbench
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# 我該測試什麼？{#what-should-i-test}

測試結果必須清晰且有意義，讓您有信心根據這些結果做出重大決策。

雖然您可以使用和網站來測試各種頁面版面，但Adobe建議您專注於測試高價值、策略性的商業計畫，或新的或重新設計的網站功能，以符合您為網站及業務所設定的目標。 [!DNL Sensor] 您可以測試最佳價格保證、個人化功能、市場優惠（例如套件或組合）、創意設計和應用程式程式等問題。

在開發受控實驗時，下列概念最為重要：

* **瞭解要進行的適當變更。** 這需要對網站的運作方式以及前端網站的相關業務流程進行一些研究。 您想要進行可提供最大影響力且可輕鬆測試的變更。
* **小型變更可產生顯著影響。** 並非您測試的所有變更都需要大幅變更，才能對您的業務產生重大影響。 隨時開放進行小型但非常重要的變更。

## 支援的方法 {#section-1071adaf54c64ba9bc5ef228c4a23635}

使用網站可進行多種不同目標的實驗。 下列清單提供一些範例：

* 變更頁面、內容和網站程式，以提高轉換率。
* 變更行銷宣傳、促銷、交叉銷售和向上銷售以增加收入。
* 變化頁面載入時間，以瞭解客戶的服務品質和基礎架構效能的實際價值。

為達成這些目標，網站支援下列類型的受控實驗和測試方法：

* **頁面取代：** 將靜態URL X取代為靜態URL Y。此方法在動態環境中的使用有限。
* **動態URI替換：** 這是「頁面取代」的變體，以動態頁面Y取代靜態頁面X，以呈現動態內容。
* **物件取代：** 將固定物件X取代為固定物件Y。
* **內容取代：** 將內容集X（多個物件、頁面、表格等）取代為內容集Y。
* **實驗變數取代：** 將JavaScript物件/writeCookie_X.js取代為JavaScript物件/writeCookie_Y.js，以編寫可供後端系統用來提供特定內容的Cookie。

>[!NOTE]
>
>受控實驗是基於URI替換，而不是查詢字串替換。 以下範例會反白顯示特定URL中的URI:
>
>`http://www.omniture.com/index.asp?id=1`
>
>例如，在您的受控實驗中，您可以指定將控制群組URI [!DNL index.asp] 取代為測試群組URI [!DNL index2.asp] ，以判斷哪個頁面設計會產生更多值。