---
description: 此檔案不僅可當成工作表，還可當成您對實驗決策的記錄。
solution: Insight,Analytics
title: 實驗設計試算表
topic: Data workbench
uuid: bcb11e39-9cbd-400c-af30-4b1c85e7f218
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 實驗設計試算表{#experiment-design-spreadsheet}

此檔案不僅可當成工作表，還可當成您對實驗決策的記錄。

如果您需要設計實驗的協助，可以使用Adobe提供的實驗設計試算表（預設命名為VS Controlled Experity Design.xls）。

實驗設計試算表只有當相關量度定義為符合某些條件的訪客百分比時，才能提供有用的統計推理。 也就是說，只有在測試訪客型度量假設時，它才有用。

**若要使用實驗設計檔案來設計您的實驗**

1. 如果您擁有Web或應用程式伺服器的管理員存取權，請導覽至Web叢 [!DNL Sensor] 集中任何機器 [!DNL Sensor] 上的安裝資料夾。 如果您沒有管理員存取權，請連絡您的Adobe客戶經理以請求檔案。
1. 開啟VS Controlled Experite Design.xls檔案。 （您可視需要重新命名此檔案。）

   下頁的試算表範例，說明您在準備測試本指南中使用的範例假設時，要如何完成試算表。

   ![](assets/experimentdesigntop.png)

   ![](assets/experimentdesignmiddle.png)

   ![](assets/experimentdesignbottom.png)

1. 為此檔案中所有以藍色表示的欄位輸入文本或值，下表將說明這些欄位。 計算欄位在第二表中定義。

<table id="table_C343F7A4BF3D4E0E9A5E9739EC7C2E10"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 在這個領域…… </th> 
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
   <td colname="col2"> <p>實驗所依據的量度名稱。 </p> <p>範例：訪客轉換 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度定義 </td> 
   <td colname="col2"> <p>實驗所依據的量度定義。 </p> <p>格式：訪客[X]/訪客 </p> <p>範例：訪 <span class="filepath"> 客[URI='conversionpage.asp']/訪客</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預期的開始時間 </td> 
   <td colname="col2"> 您希望實驗開始的日期和時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預期結束時間 </td> 
   <td colname="col2"> 您希望實驗結束的日期和時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 適用選擇 </td> 
   <td colname="col2"> （可選）您要進一步分段資料集的維度名稱和元素集或範圍。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 實驗URI </td> 
   <td colname="col2"> 你的假設中涉及的URI。 您為控制組定義當前URI，以及為測試組建立或將建立的備用URI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 應用程式選擇的預期量度 </td> 
   <td colname="col2"> 您預期網站的量度值標題。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每日平均訪客數 </td> 
   <td colname="col2"> 每天瀏覽您網站的平均訪客數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客轉換 </td> 
   <td colname="col2"> 您網站的平均訪客轉換率。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 實驗將決定測試群組的量度名稱是否為…… </td> 
   <td colname="col2"> 度量值比較的標題。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 大於控制組的值？ </td> 
   <td colname="col2"> 如果您想要得出測試群組的量度在實驗期間增加的結論，請將此欄位設為True。 將此欄位設為False可減少得出結論所需的訪客數。 Adobe建議您將其設為True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 小於控制組的值？ </td> 
   <td colname="col2"> 如果您想要判斷測試群組的量度在實驗期間減少，請將此欄位設為True。 Adobe建議您將其設為True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 至少（檢測級別） </td> 
   <td colname="col2"> 您希望測試群組的量度高於或低於控制群組的量度的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 至少具有 </td> 
   <td colname="col2"> 測試群組值的所需信賴等級。 信賴等級會決定誤報數目，用以測量所述期望為真的概率。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 和 </td> 
   <td colname="col2"> 測試群組值所需的功率等級。 電源級別決定了虛假負片的數量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> %的訪客 </td> 
   <td colname="col2"> 訪客值百分比的標題。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 測試群組 </td> 
   <td colname="col2"> 您要納入測試群組的訪客百分比。 您可以播放此數字，直到「訪客」區段的「總計（通常為100%）」欄位中的值等於或大於「需要的最小訪客（測試+控制群組）」欄位中的值，下表將說明兩者。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 控制組 </td> 
   <td colname="col2"> 您要納入控制群組的訪客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 其他設計注意事項 </td> 
   <td colname="col2"> 您要儲存的任何附註，以供日後參考。 </td> 
  </tr> 
 </tbody> 
</table>

其餘欄位是根據您所輸入的值計算，並於下表中說明。

| 欄位 | 說明 |
|---|---|
| 應用程式選擇的預期量度 | 您預期網站的量度值標題。 |
| 每個時段的預期訪客 | 此欄位通常由試算表自動計算。 這要視網站在大多數日子裡接收的新訪客比回訪訪客多的假設而定。 若非如此，則此儲存格的計算應覆寫為實驗期間預期的實際訪客數。 |
| I類錯誤的計算Z分數 | 假陽性結果的Z分數。 這是一種中間統計計算。 |
| 計算II類型錯誤的Z分數 | 假負結果的Z分數。 這是一種中間統計計算。 |
| 需要的最低訪客數（測試+控制群組） | 符合您指定信賴等級、功率等級和Z分數的實驗所需最小訪客數，以「每時段預期訪客」欄位中值的百分比表示。 |
| 需要的最低訪客數（測試+控制群組） | 符合您指定信賴等級、功率等級和Z分數之實驗所需的最小訪客數。 此值必須小於或等於「訪客」區段中「總計」（通常為100%）欄位中的值。 |
| 最小實驗時間（天） | 執行實驗所需的最少天數，以符合您指定的信賴等級、功率等級和Z分數。 此計算量度所受的問題與「每個時段的預期訪客」欄位中討論的問題相同。 若網站有許多舊訪客，「最小實驗時間（天數）」欄位是「需要最少訪客」欄位中的值，所需的預期天數。 |
| 訪客 | 訪客值的標題。 |
| 測試群組 | 測試群組中所需的訪客數。 |
| 控制組 | 控制群組中所需的訪客數。 |
| 總計（通常為100%） | 實驗所需的訪客總數。 此值必須等於或大於「所需最小訪客數（測試+控制群組）」欄位中的值。 |
| 測試群組正確性（在目標信賴等級） | 百分比表示有機會等於指定的信賴等級，為測試群組計算的量度測量值將在其實際值的這個百分比內。 |
| 控制群組正確性（在目標信賴等級） | 百分比表示有機會等於指定的信賴等級，為控制群組計算的量度測量值將在其實際值的這個百分比內。 |
| Z分數（目標準確度） | 給定值與測試平均值的標準差數。 |
| 實際信賴等級（在目標間隔） | 實驗達到的置信度。 信賴等級會測量所陳述之預期為真的可能性。 |
| 實際間隔（在目標信賴等級） | 該實驗所實現的置信區間，該置信區間提供可能包括未知種群參數的估計值範圍。 此範圍是根據一組給定的樣本資料計算的。 |

您必須在「所需最少訪客數（測試+控制群組）」欄位中查看值。..

![](assets/Experiment_Design_Min_Visitors.png)

並將它與欄中「總計」欄位中的值進行 [!DNL Visitors] 比較。

![](assets/Experiment_Design_Total_Visitors.png)

若要讓實驗在統計上有效，「總計」（通常為100%）欄位中的值必須等於或大於「所需最小訪客數」（「測試+控制群組」）欄位中的值。

根據提供的輸入，範例工作表顯示，有10,475位訪客需要參與此實驗，才能達到輸入的95%信賴率（這是任何受控實驗的建議最低信賴率，不過您可以增加此數目）。 目前設計的實驗包括30,000位訪客，遠高於所需的最低訪客數。

如果您將天數維持不變，則只要訪客總數持續滿足或超過所需的最小值，您就可以提高信賴等級。

1. 儲存記錄的檔案，然後使用檔案中的資訊，使用實驗設定試算表來設定實驗。 如需此試算表的詳細資訊，請參 [閱設定和部署實驗](../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)。
