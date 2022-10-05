---
description: 此檔案不僅可作為工作表，也可作為您對實驗決策的記錄。
solution: Analytics
title: 實驗設計試算表
uuid: bcb11e39-9cbd-400c-af30-4b1c85e7f218
exl-id: 554790ab-1182-4481-87b0-e768ea769ddf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# 實驗設計試算表{#experiment-design-spreadsheet}

{{eol}}

此檔案不僅可作為工作表，也可作為您對實驗決策的記錄。

如果您需要設計實驗的協助，可以使用Adobe提供的實驗設計試算表（預設為VS Controlled Experience Design.xls）。

只有當相關量度定義為符合某些條件的訪客百分比時，實驗設計試算表才能提供有用的統計推斷。 也就是說，只有在測試以訪客為基礎的量度假設時才有用。

**使用實驗設計檔案設計實驗**

1. 如果您有Web或應用程式伺服器的管理員存取權，請導覽至 [!DNL Sensor] 任何 [!DNL Sensor] 電腦。 如果您沒有管理員存取權，請連絡您的Adobe帳戶管理員以要求檔案。
1. 開啟VS Controlled Experience Design.xls檔案。 （您可以視需要重新命名此檔案。）

   以下頁面的試算表範例說明您準備測試本指南中使用的範例假設時，如何填妥試算表。

   ![](assets/experimentdesigntop.png)

   ![](assets/experimentdesignmiddle.png)

   ![](assets/experimentdesignbottom.png)

1. 輸入此檔案中以藍色表示的所有欄位的文本或值，如下表所述。 計算欄位在第二個表格中定義。

<table id="table_C343F7A4BF3D4E0E9A5E9739EC7C2E10"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 在這個欄位…… </th> 
   <th colname="col2" class="entry"> 指定分類的 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 實驗標題 </td> 
   <td colname="col2"> 實驗的描述性名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 實驗說明 </td> 
   <td colname="col2"> 實驗的文本描述。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 正在研究的量度 </td> 
   <td colname="col2"> <p>實驗所依據之量度的名稱。 </p> <p>範例：訪客轉換 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度定義 </td> 
   <td colname="col2"> <p>實驗所依據之量度的定義。 </p> <p>格式：訪客[X]/訪客 </p> <p>範例： <span class="filepath"> Visitors[URI='conversionpage.asp']/Visitors</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預定開始時間 </td> 
   <td colname="col2"> 您要開始實驗的日期和時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預期結束時間 </td> 
   <td colname="col2"> 您希望實驗結束的日期和時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 適用的選擇 </td> 
   <td colname="col2"> （選用）您要進一步劃分資料集的維度名稱和元素集或範圍。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 實驗URI </td> 
   <td colname="col2"> 你的假設中涉及的URI。 為控制組定義當前URI，為已建立或將為測試組建立的替代URI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 應用程式選擇的預期度量 </td> 
   <td colname="col2"> 標題為您預期網站的量度值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每日平均訪客數 </td> 
   <td colname="col2"> 每天瀏覽您網站的平均訪客數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客轉換 </td> 
   <td colname="col2"> 網站的平均訪客轉換率。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 實驗將判斷測試群組的量度名稱是否為…… </td> 
   <td colname="col2"> 比較量度值的標題。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 是否大於控制組的值？ </td> 
   <td colname="col2"> 如果您想要能夠得出測試群組的量度在實驗期間增加的結論，請將此欄位設為True。 將此欄位設為False ，以減少得出結論所需的訪客數量。 Adobe建議將其設為True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 小於控制組的值？ </td> 
   <td colname="col2"> 如果您想要能夠得出測試群組的量度在實驗期間減少的結論，請將此欄位設為True。 Adobe建議將其設為True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 至少（檢測級別） </td> 
   <td colname="col2"> 您希望測試群組的量度高於或低於控制群組的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 至少具有 </td> 
   <td colname="col2"> 測試群組值所需的信賴等級。 信賴等級會決定誤判的數量，以測量指出的期望為真的機率。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 以及 </td> 
   <td colname="col2"> 測試組值所需的功率級別。 電源級別決定偽負數的數量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客百分比 </td> 
   <td colname="col2"> 代表訪客值百分比的標題。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 測試群組 </td> 
   <td colname="col2"> 您要包含在測試群組中的訪客百分比。 您可以播放此數字，直到「訪客」區段中「總計」（通常為100%）欄位中的值等於或大於「最小需要訪客數」（「測試+控制群組」）欄位中的值為止，下表將說明這兩者。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 控制組 </td> 
   <td colname="col2"> 您要包含在控制群組中的訪客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 其他設計附註 </td> 
   <td colname="col2"> 要保存以供將來參考的任何注釋。 </td> 
  </tr> 
 </tbody> 
</table>

其餘欄位會根據您輸入的值計算，如下表所述。

| 欄位 | 說明 |
|---|---|
| 應用程式選擇的預期度量 | 標題為您預期網站的量度值。 |
| 每個時段的預期訪客數 | 此欄位通常會由試算表自動計算。 這有賴於以下假設：在大多數日子裡，網站接收的新訪客比回訪訪客多很多。 若非如此，則此儲存格的計算應覆寫為實驗期間預期的實際訪客數。 |
| I類錯誤的計算Z分數 | 誤判結果的Z分數。 這是中間的統計計算。 |
| 第II類錯誤的計算Z分數 | 誤判結果的Z分數。 這是中間的統計計算。 |
| 最低需要訪客數（測試+控制群組） | 在實驗中符合指定信賴等級、冪等級和Z分數所需的最小訪客數，以「每期預期訪客數」欄位中值的百分比表示。 |
| 最低需要訪客數（測試+控制群組） | 實驗中需要的最小訪客數，以符合您指定的信賴等級、電源等級及Z分數。 此值必須小於或等於「訪客」區段中「總計」（通常為100%）欄位中的值。 |
| 最小實驗時間（天） | 執行實驗以符合指定信賴等級、電源等級和Z分數所需的最少天數。 此計算量度所受的問題與「每期預期訪客」欄位中討論的問題相同。 若是網站有許多回訪的訪客，「最低實驗時間（天）」欄位是預期的天數，可檢視多個不重複訪客，等於「最低需要訪客數」欄位中的值。 |
| 訪客 | 訪客值的標題。 |
| 測試群組 | 測試群組中需要的訪客數。 |
| 控制組 | 控制組中需要的訪客數。 |
| 總計（通常為100%） | 實驗所需的訪客總數。 此值必須等於或大於「需要的最小訪客數」（「測試+控制群組」）欄位中的值。 |
| 測試群組準確度（在目標信賴等級） | 百分比表示有機會等於指定的信賴等級，為測試群組計算的量度的測量值將在其真實值的這個百分比內。 |
| 控制組準確度（在目標信賴等級） | 百分比表示有機會等於指定的信賴水準，即為控制組計算的度量的測量值將在其真實值的這個百分比內。 |
| Z分數（在目標準確度上） | 指定值與測試平均值的標準差數。 |
| 實際信賴等級（目標區間） | 實驗的信賴水準。 信賴水準會測量所述預期為真的機率。 |
| 實際間隔（目標信賴等級） | 實驗的信賴區間，提供可能包含未知母體參數的估計值範圍。 此範圍是根據一組指定的範例資料計算。 |

您需要查看「所需最低訪客數（測試+控制群組）」欄位中的值。..

![](assets/Experiment_Design_Min_Visitors.png)

並與 [!DNL Visitors] 欄。

![](assets/Experiment_Design_Total_Visitors.png)

為了讓實驗在統計上有效，「總計」（通常為100%）欄位中的值必須等於或大於「需要的最小訪客數」（「測試+控制群組」）欄位中的值。

根據提供的輸入，範例工作表顯示，有10,475位訪客需要參與此實驗，才能達到輸入的95%信賴率（這是任何受控實驗的最低建議信賴率，不過您可以增加此數量）。 目前設計的實驗包含30,000位訪客，遠高於所需的最低訪客數。

如果保持相同的天數，只要訪客總數持續達到或超過所需的最小值，您就可以提高信賴等級。

1. 儲存檔案以供記錄使用，然後使用檔案中的資訊，使用實驗設定試算表來設定實驗。 如需此試算表的詳細資訊，請參閱 [設定和部署實驗](../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).
