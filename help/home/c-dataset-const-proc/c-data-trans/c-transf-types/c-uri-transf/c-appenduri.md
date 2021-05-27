---
description: AppendURI轉換提供了一種方法，可將資訊添加到預設值中，該預設值來自用於構建資料集的日誌條目。
title: AppendURI
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
exl-id: 0d5901c0-bd13-4499-8e26-44839aeb7413
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 1%

---

# AppendURI{#appenduri}

AppendURI轉換提供了一種方法，可將資訊添加到預設值中，該預設值來自用於構建資料集的日誌條目。

轉換會將名稱值對放置在用於建立URI維的內部欄位的末尾。 名稱值組是使用查詢字串鍵參數作為名稱構建的，而標識的輸入參數的值作為對的值。 [!DNL AppendURI]命令添加任何適當的？ 和必要的&amp;符號，用於將名稱值對從[!DNL URI]莖區和可能已應用到URI的任何先前[!DNL AppendURI]操作中分離出來。

[!DNL AppendURI]轉換只有在[!DNL Transformation.cfg]檔案或[!DNL Transformation Dataset Include]檔案中定義時才有效。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。轉換的相關附註。 |  |
| 條件 | 套用此轉換的條件。 |  |
| 預設 | 在符合條件且輸入值不可用時使用的預設值。 |  |
| 輸入 | 其值附加到URI的欄位的名稱。 |  |
| 查詢字串索引鍵 | 建立要附加的名稱值對時使用的名稱。 |  |

考慮使用傳統模型 — 視圖 — 控制器方法構建的網站。 在這類系統中，通常使用單個網頁作為系統的訪問點。 對於這類網站，系統中的流量模式視覺化將非常無趣，不會提供訪客使用率和流量的深入分析。 例如，假設有一個網站，可透過下列格式的URI匯集所有Web請求：

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

模型檢視ASP頁面會接收所有流量，並根據查詢中id欄位的值來決定其動作。 預設情況下，URI維將包含單個條目：

* [!DNL modelview.asp]

這會導致對整個網站的流量進行相當無趣的對應，因為所有流量都會透過單一URI輸送。 要解決此特定情況，並為網站的基礎架構提供更豐富的視圖，[!DNL AppendURI]可用來將一些唯一名稱值對從cs-uri-query欄位移到用於視覺效果的URI維。 以下所示的轉換提供此類轉換的詳細資訊：

![](assets/cfg_TransformationType_AppendURI.png)

在此範例中，系統使用兩個頁面來處理所有請求：[!DNL modelview.asp]和[!DNL xmlmodelview.asp]。 一個頁面用於瀏覽器流量，另一個頁面用於系統對系統XML通訊。 應用程式伺服器進程使用cs-uri-query的ID名稱來確定要執行的操作。 因此，您可以從id欄位中擷取值，並將其附加至URI。 結果會是URI的集合，其變數範圍會反映網站上的訪客流量。 在此，[!DNL String Match]條件通過搜索感興趣的兩個網頁的cs-uri-stem欄位並忽略所有其它網頁來確定應用轉換的日誌條目。 輸入（名稱值對的值）是cs-uri-query(id)的結果，即「login」。 如查詢字串索引鍵參數所指定，所附加的名稱為「id」。 因此，對於我們示例的傳入cs-uri值，[!DNL URI]維使用的結果URI為[!DNL /modelview.asp&id=login]。
