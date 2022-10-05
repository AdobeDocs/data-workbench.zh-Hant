---
description: 隨Insight Server安裝的檔案清單，以及在註冊後存在且首次執行的檔案。
title: Insight Server 目錄結構
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# Insight Server 目錄結構{#insight-server-directory-structure}

{{eol}}

隨Insight Server安裝的檔案清單，以及在註冊後存在且首次執行的檔案。

## 安裝套件中包含的檔案 {#section-daec17dab3e34c3c9e1ef65842cb91f1}

下列目錄包含在 [!DNL Insight Server] 安裝套件：

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 目錄 </th> 
   <th colname="col2" class="entry"> 目錄內容說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 存取控制 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> 指定訪問組清單的配置檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> 用於與通信的地址 <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 稽核 </td> 
   <td colname="col2"> 每日訪問日誌，其中包含與所有嘗試連接有關的詳細資訊 <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> 可執行程式檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 憑證 </td> 
   <td colname="col2"> SSL數位憑證。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 元件 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> 元件組態檔。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 處理伺服器的元件 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> 處理元件組態檔 <span class="keyword"> Insight Server </span> 在 <span class="keyword"> Insight Server </span> 群集。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 活動 </td> 
   <td colname="col2"> 包含詳細事件狀態訊息（包括錯誤訊息）的每日事件記錄。 捕獲和記錄的事件 <span class="keyword"> Insight Server </span> 也顯示在Windows事件查看器中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 記錄檔 </td> 
   <td colname="col2"> <p>由生成的日誌檔案 <span class="wintitle"> 感測器 </span>(s)。 </p> <p>「Logs」是預設記錄目錄，但可能已在 <span class="filepath"> communications.cfg </span> 檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 查閱 </td> 
   <td colname="col2"> 查閱檔案，例如自動機和搜尋引擎清單。 <span class="keyword"> Insight Server </span> 必須將所有查閱檔案載入記憶體中。 元件配置檔案中引用的所有查閱檔案的總大小，加上開銷(例如，每行12個位元組 <span class="filepath"> FlatFileLookup </span> 檔案)，不得超過載入所有其他軟體應用程式後可用的可用物理或虛擬記憶體。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 設定檔 </td> 
   <td colname="col2"> <p>與每個設定檔相關的檔案（設定、工作區和視覺效果檔案）。 設定檔會由資料集的資料填入。 資料集包括事件資料（「記錄資料」）;這些資料可通過安裝來捕獲 <span class="wintitle"> 感測器 </span>、由Web信標或頁面標籤傳送，或從資料倉庫輸入。 <span class="keyword"> 分析 </span> 具有指定設定檔存取權的使用者可以使用該設定檔的處理資料集，以及該設定檔中定義的工作區和視覺效果。 </p> <p>工作區是系統管理或分析的工作區。 工作區可包含多個介面，顯示有關係統效能的不同詳細資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 軟體 </td> 
   <td colname="col2"> <span class="keyword"> 分析 </span> 軟體更新。 報告軟體更新也儲存在此處。 </td> 
  </tr> 
 </tbody> 
</table>

## 啟動後建立的目錄和檔案 {#section-ef7408e8fae64454b326ec07453d4628}

下列目錄是在 [!DNL Insight Server] 已註冊並首次運行：

<table id="table_89CC9F3E568044C8A0072BF0A6EDCCEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 目錄 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 州別 </td> 
   <td colname="col2"> 處理由生成的資訊 <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 臨時 </td> 
   <td colname="col2"> <p>使用的臨時檔案的位置 <span class="keyword"> Insight Server </span> 進行重新處理和操作時。 通常有一個檔案(名為 <span class="filepath"> temp.db </span> 預設)。 </p> <p> <span class="keyword"> Insight Server </span> 必須配置為寫入此目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trace </td> 
   <td colname="col2"> 記錄和事件資料關於 <span class="keyword"> Insight Server </span>. 疑難排解很實用。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 用戶 </td> 
   <td colname="col2"> 已命名( <span class="keyword"> 分析 </span>)可存取伺服器上設定檔的使用者。 當用戶首次訪問時，將在「用戶」目錄中建立每個授權命名用戶的目錄 <span class="keyword"> Insight Server </span> via <span class="keyword"> 分析 </span>. 每個指名用戶的目錄包含與用戶訪問的所有配置檔案對應的目錄 <span class="keyword"> Insight Server </span> 以及其本地地址檔案。 </td> 
  </tr> 
 </tbody> 
</table>
