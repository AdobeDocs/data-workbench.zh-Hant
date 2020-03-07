---
description: AppendURI轉換提供了一種方法，可將資訊添加到預設值中，該預設值來自用於構建資料集的日誌條目。
solution: Analytics
title: AppendURI
topic: Data workbench
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# AppendURI{#appenduri}

AppendURI轉換提供了一種方法，可將資訊添加到預設值中，該預設值來自用於構建資料集的日誌條目。

轉換將名稱——值對放置在用於建立URI維的內部欄位的末尾。 名稱——值對是使用查詢字串鍵參數作為名稱，而已識別的輸入參數值作為對的值構建的。 命 [!DNL AppendURI] 令添加任何適當？ 和&amp;符號，以便將名稱值對與stem以及任何 [!DNL URI] 先前可能已套用 [!DNL AppendURI] 至URI的操作分開。

只有在 [!DNL AppendURI] 檔案或檔案中定義時， [!DNL Transformation.cfg] 轉換才可 [!DNL Transformation Dataset Include] 用。

| 參數 | 說明 | 預設值 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 意見 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 預設值 | 如果條件符合且輸入值不可用，則使用的預設值。 |  |
| 輸入 | 值附加到URI的欄位的名稱。 |  |
| 查詢字串索引鍵 | 建立要附加的名稱——值對時要使用的名稱。 |  |

考慮使用傳統模型——視圖——控制器方法構建的網站。 在這類系統中，通常使用單一網頁作為系統的存取點。 對於這類網站，系統中流量模式的視覺化將非常不有趣，不會提供訪客使用率和流量的深入資訊。 例如，假設網站會透過下列格式的URI來傳送所有Web要求：

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

模型檢視ASP頁面會接收所有流量，並根據查詢中id欄位的值來決定其動作。 預設情況下，URI維將包含一個條目：

* [!DNL modelview.asp]

這會導致對於透過網站的流量產生相當不有趣的對應，因為所有流量都會透過單一URI來輸送。 若要解決此特定情形，並提供網站基礎架構的更豐富資訊檢視， [!DNL AppendURI] 可用來將某些唯一名稱——值配對從cs-uri-query欄位移至用於視覺化的URI維度。 下面顯示的轉換提供了此類轉換的詳細資訊：

![](assets/cfg_TransformationType_AppendURI.png)

在此範例中，系統使用兩個頁面來處理所有請求： [!DNL modelview.asp] 和 [!DNL xmlmodelview.asp]。 一個頁面用於瀏覽器流量，另一個頁面用於系統間XML通訊。 應用程式伺服器程式會使用cs-uri-query的ID名稱來決定要採取的動作。 因此，您可從id欄位擷取值並附加至URI。 結果是一組URI，其變化範圍會反映網站的訪客流量。 在此，條 [!DNL String Match] 件會透過搜尋目標網頁的cs-uri-stem欄位並忽略所有其他網頁，來決定套用轉換的記錄項目。 輸入（我們的名稱——值對的值）是cs-uri-query(id)的結果，即「login」。 如查詢字串索引鍵參數所指定，所附加的名稱為&quot;id&quot;。 因此，對於我們示例的傳入cs-uri值，維所使用的結果URI [!DNL URI] 是 [!DNL /modelview.asp&id=login]。
