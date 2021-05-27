---
description: 隨Insight Server安裝的檔案清單，以及在註冊後存在且首次執行的檔案。
title: Insight Server 目錄結構
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---

# Insight Server 目錄結構{#insight-server-directory-structure}

隨Insight Server安裝的檔案清單，以及在註冊後存在且首次執行的檔案。

## 安裝套件中包含的檔案 {#section-daec17dab3e34c3c9e1ef65842cb91f1}

[!DNL Insight Server]安裝包中包括以下目錄：

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
   <td colname="col2"> <span class="keyword"> 指定存 </span> 取群組清單的Insight Server設定檔。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> 用於與<span class="keyword"> Insight Server </span>通訊的地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 稽核 </td> 
   <td colname="col2"> 每日存取記錄檔包含與<span class="keyword"> Insight Server </span>所有嘗試連線的詳細資訊。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Insight Server可執 </span> 行程式檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 憑證 </td> 
   <td colname="col2"> SSL數位憑證。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 元件 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server元 </span> 件組態檔。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 處理伺服器的元件 </td> 
   <td colname="col2"> <span class="keyword"> 用於處 </span> 理Insight Server叢集中 <span class="keyword"> Insight Server的 </span> Insight Server元 <span class="keyword"> 件設 </span> 定檔。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 包含詳細事件狀態訊息（包括錯誤訊息）的每日事件記錄。 由<span class="keyword"> Insight Server </span>擷取和記錄的事件也會顯示在Windows事件檢視器中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 記錄檔 </td> 
   <td colname="col2"> <p>由<span class="wintitle">感測器</span>(s)生成的日誌檔案。 </p> <p>"Logs"是預設記錄目錄，但在<span class="filepath"> communications.cfg </span>檔案中可能已指定替代目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 查閱 </td> 
   <td colname="col2"> 查閱檔案，例如自動機和搜尋引擎清單。 <span class="keyword"> Insight Server必須 </span> 將所有查閱檔案載入記憶體中。元件配置檔案中引用的所有查找檔案的總大小加上開銷（例如，<span class="filepath"> FlatFileLookup </span>檔案的每行12位元組），不得超過載入所有其他軟體應用程式後可用的可用物理或虛擬記憶體。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 設定檔 </td> 
   <td colname="col2"> <p>與每個設定檔相關的檔案（設定、工作區和視覺效果檔案）。 設定檔會由資料集的資料填入。 資料集包括事件資料（「記錄資料」）;此類資料可由安裝的<span class="wintitle">感測器</span>捕獲，由Web信標或頁面標籤傳輸，或從資料倉庫輸入。 <span class="keyword"> 可存 </span> 取指定設定檔的Insight使用者可能會使用該設定檔的已處理資料集，以及該設定檔中定義的工作區和視覺效果。 </p> <p>工作區是系統管理或分析的工作區。 工作區可包含多個介面，顯示有關係統效能的不同詳細資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 軟體 </td> 
   <td colname="col2"> <span class="keyword"> Insight </span> 軟體更新。報告軟體更新也儲存在此處。 </td> 
  </tr> 
 </tbody> 
</table>

## 啟動後建立的目錄和檔案{#section-ef7408e8fae64454b326ec07453d4628}

以下所列的目錄在註冊並首次運行[!DNL Insight Server]後建立：

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
   <td colname="col2"> 處理由<span class="keyword"> Insight Server </span>產生的資訊。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 臨時 </td> 
   <td colname="col2"> <p><span class="keyword"> Insight Server </span>在重新處理和操作期間使用的臨時檔案的位置。 每個物理驅動器通常有一個檔案（預設名為<span class="filepath"> temp.db </span>）。 </p> <p> <span class="keyword"> Insight Server必 </span> 須設定為寫入此目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trace </td> 
   <td colname="col2"> 記錄<span class="keyword"> Insight Server </span>的相關事件資料。 疑難排解很實用。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用者 </td> 
   <td colname="col2"> 已命名（<span class="keyword">分析</span>）可存取伺服器上設定檔的使用者。 當使用者首次透過<span class="keyword"> Insight </span>存取<span class="keyword"> Insight Server </span>時，系統會在「使用者」目錄內建立每個已授權指名使用者的目錄。 每個指名用戶的目錄包含與用戶在該<span class="keyword"> Insight Server </span>上訪問的所有配置檔案以及其本地地址檔案相對應的目錄。 </td> 
  </tr> 
 </tbody> 
</table>
