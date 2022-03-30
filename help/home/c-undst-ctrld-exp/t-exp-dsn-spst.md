---
description: 此檔案不僅用作工作表，還用作您對實驗決策的記錄。
solution: Analytics
title: 實驗設計試算表
uuid: bcb11e39-9cbd-400c-af30-4b1c85e7f218
exl-id: 554790ab-1182-4481-87b0-e768ea769ddf
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# 實驗設計試算表{#experiment-design-spreadsheet}

此檔案不僅用作工作表，還用作您對實驗決策的記錄。

如果需要設計實驗的幫助，可以使用Adobe提供的實驗設計電子錶格（預設名為VS Controlled Experite Design.xls）。

只有當所討論的度量被定義為滿足某些標準的訪問者的百分比時，實驗設計電子錶格才能提供有用的統計推斷。 也就是說，只有在測試基於訪問者的度量假設時，它才有用。

**使用實驗設計檔案設計實驗**

1. 如果您對Web或應用程式伺服器具有管理員訪問權限，請導航到 [!DNL Sensor] 安裝資料夾 [!DNL Sensor] 電腦。 如果您沒有管理員訪問權限，請與Adobe帳戶經理聯繫以請求該檔案。
1. 開啟VS Controlled Experiment Design.xls檔案。 （如果需要，可以更名此檔案。）

   下頁上的電子錶格是準備test本指南中使用的示例假設時如何完成電子錶格的示例。

   ![](assets/experimentdesigntop.png)

   ![](assets/experimentdesignmiddle.png)

   ![](assets/experimentdesignbottom.png)

1. 為此檔案中藍色的所有欄位輸入文本或值，下表對此進行了說明。 計算的欄位在第二個表中定義。

<table id="table_C343F7A4BF3D4E0E9A5E9739EC7C2E10"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 在此欄位中…… </th> 
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
   <td colname="col1"> 正在研究的度量 </td> 
   <td colname="col2"> <p>實驗所基於的度量的名稱。 </p> <p>示例：訪問者轉換 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 度量定義 </td> 
   <td colname="col2"> <p>實驗所基於的度量的定義。 </p> <p>格式：訪問者[X]/訪問者 </p> <p>示例： <span class="filepath"> 訪問者[URI='conversionpage.asp']/訪問者</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預期開始時間 </td> 
   <td colname="col2"> 希望實驗開始的日期和時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預期結束時間 </td> 
   <td colname="col2"> 希望實驗結束的日期和時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 適用選擇 </td> 
   <td colname="col2"> （可選）要進一步劃分資料集的維名稱和元素集或範圍。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 實驗URI </td> 
   <td colname="col2"> 你的假設所涉及的URI。 您為控制組定義當前URI以及為test組建立或將建立的備用URI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 應用程式選擇的預期度量 </td> 
   <td colname="col2"> 標題為您期望的網站度量值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每天平均訪問者數 </td> 
   <td colname="col2"> 每天訪問您網站的平均訪問者數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者轉換 </td> 
   <td colname="col2"> 網站的平均訪問者轉換率。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 實驗將確定Test組的度量名稱是否為…… </td> 
   <td colname="col2"> 用於比較度量值的標題。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 是否大於控制組的值？ </td> 
   <td colname="col2"> 如果希望能夠得出test組度量在實驗期間增加的結論，請將此欄位設定為True。 將此欄位設定為False可減少得出結論所需的訪問者數。 Adobe建議將其設定為True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 是否小於控制組的值？ </td> 
   <td colname="col2"> 如果希望能夠得出test組度量在實驗期間減少的結論，請將此欄位設定為True。 Adobe建議將其設定為True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 至少按（檢測級別） </td> 
   <td colname="col2"> 希望test組的度量比控制組的度量高或低的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 至少具有 </td> 
   <td colname="col2"> 所需的test組值置信度。 置信度確定誤報數量以測量所述期望為真的概率。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 和電源級別 </td> 
   <td colname="col2"> test組值的所需功率級。 電源級確定假負數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者百分比 </td> 
   <td colname="col2"> 標題為訪問者值的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Test組 </td> 
   <td colname="col2"> 要包括在test組中的訪問者百分比。 您可以使用此數字進行播放，直到「訪問者」部分的「合計（通常為100%）」欄位的值等於或大於「最小需要訪問者(Test+控制組)」欄位中的值，下表均對這兩個值進行了說明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 控制組 </td> 
   <td colname="col2"> 要包括在控制組中的訪問者百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 其他設計說明 </td> 
   <td colname="col2"> 要保存的任何注釋以供將來參考。 </td> 
  </tr> 
 </tbody> 
</table>

其餘欄位根據您輸入的值進行計算，並在下表中進行說明。

| 欄位 | 說明 |
|---|---|
| 應用程式選擇的預期度量 | 標題為您期望的網站度量值。 |
| 每個期間的預期訪問者 | 此欄位通常由電子錶格自動計算。 它基於這樣一個假設：在大多數日子裡，網站接待的新訪問者比回訪者多得多。 如果不是這樣，則此單元格的計算應被實驗期間預期的實際訪問者數覆蓋。 |
| 計算I類錯誤的Z得分 | 假陽性結果的Z得分。 這是一個中間統計計算。 |
| 計算II類錯誤的Z得分 | 假陰性結果的Z得分。 這是一個中間統計計算。 |
| 所需訪問者最少(Test+控制組) | 在實驗中滿足指定置信度、功率級和Z分數所需的最小訪問者數，以「每個期間的預期訪問者」欄位中的值的百分比表示。 |
| 所需訪問者最少(Test+控制組) | 在實驗中滿足指定的置信度、功率和Z分數所需的訪問者的最小數量。 此值必須小於或等於「訪問者」部分「合計」（通常為100%）欄位中的值。 |
| 最小實驗時間（天） | 運行實驗以滿足指定的置信度、電源級別和Z分數所需的最少天數。 此計算的數字受與「每個期間的預期訪問者」欄位中討論的問題相同的限制。 對於具有多個返回訪問者的網站，「最小實驗時間（天數）」欄位是查看與「所需最少訪問者數」欄位中的值相等的多個唯一訪問者所需的預期天數。 |
| 訪客 | 為訪問者值標題。 |
| Test組 | test組所需的訪問者數。 |
| 控制組 | 控制組中所需的訪問者數。 |
| 合計（通常為100%） | 實驗所需訪問者總數。 此值必須等於或大於「需要的最小訪問者(Test+控制組)」欄位中的值。 |
| Test組精度（目標置信度） | 百分比，表示存在等於指定置信度的機會，即為test組計算的度量的測量值將在其真實值的此百分比內。 |
| 控制組精度（目標置信度） | 百分比，表示存在與指定置信度相等的機會，即為控制組計算的度量的測量值將在其真實值的此百分比內。 |
| Z得分（目標精度） | 給定值與test平均值的標準偏差數。 |
| 實際置信度（目標間隔） | 實驗的置信度。 置信度測量所述期望為真的可能性。 |
| 實際間隔（目標置信度） | 為實驗實現的置信區間，它提供可能包括未知總體參數的估計值範圍。 此範圍從給定的樣本資料集計算。 |

您需要查看「需要的最小訪問者(Test+控制組)」欄位中的值。。。

![](assets/Experiment_Design_Min_Visitors.png)

並將其與 [!DNL Visitors] 的雙曲餘切值。

![](assets/Experiment_Design_Total_Visitors.png)

要使實驗在統計上有效，「總量（通常為100%）」欄位中的值必須等於或大於「所需最小訪問者(Test+控制組)」欄位中的值。

根據提供的輸入，示例工作表顯示，有10,475名訪問者需要參與此實驗，以達到輸入的95%置信度（這是任何受控實驗的最低建議置信度，儘管您可以增加此數量）。 目前設計的實驗包括3萬名參觀者，這遠遠超過了所需的最低參觀人數。

如果保持相同的天數，則只要訪問者總數繼續開會或超過所需的最小值，您就可以提高信任度。

1. 將檔案保存為記錄，然後使用檔案中的資訊使用實驗配置電子錶格配置實驗。 有關此電子錶格的詳細資訊，請參見 [配置和部署實驗](../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)。
