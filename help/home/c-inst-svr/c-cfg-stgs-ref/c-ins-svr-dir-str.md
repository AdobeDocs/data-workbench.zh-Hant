---
description: 隨Insight Server安裝的檔案清單，以及在註冊後出現的檔案，並首次執行。
solution: Analytics
title: Insight Server 目錄結構
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---


# Insight Server 目錄結構{#insight-server-directory-structure}

隨Insight Server安裝的檔案清單，以及在註冊後出現的檔案，並首次執行。

## 安裝套件中包含的檔案 {#section-daec17dab3e34c3c9e1ef65842cb91f1}

安裝軟體包中包含以下 [!DNL Insight Server] 目錄：

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
   <td colname="col2"> <span class="keyword"> Insight Server設 </span> 定檔案，指定存取群組清單。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> 用於與 <span class="keyword"> Insight Server通訊的位址 </span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 審計 </td> 
   <td colname="col2"> 每日存取記錄檔，包含所有嘗試連線至 <span class="keyword"> Insight Server的詳細資 </span>訊。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 賓 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server可執 </span> 行程式檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 憑證 </td> 
   <td colname="col2"> SSL數位憑證。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 元件 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server元 </span> 件設定檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 處理伺服器的元件 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server元 </span> 件設定檔案，用於處理 <span class="keyword"> Insight Server叢集中的Insight Server </span><span class="keyword"></span> 。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 包含詳細事件狀態消息（包括錯誤消息）的每日事件日誌。 Insight Server擷取並記錄的 <span class="keyword"> 事件也 </span> 會顯示在Windows事件檢視器中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 記錄檔 </td> 
   <td colname="col2"> <p>感測器生 <span class="wintitle"> 成的 </span>日誌檔案。 </p> <p>"Logs"是預設的記錄目錄，但可能已在communications.cfg檔案中指定 <span class="filepath"> 替代目 </span> 錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代碼 </td> 
   <td colname="col2"> 查閱檔案，例如自動機和搜尋引擎清單。 <span class="keyword"> Insight Server必 </span> 須將所有查閱檔案載入記憶體。 元件配置檔案中引用的所有查找檔案的總大小加上開銷(例如， <span class="filepath"></span> FlatFileLookup檔案的每行12位元組)不得超過載入所有其他軟體應用程式後可用的物理或虛擬記憶體。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 設定檔 </td> 
   <td colname="col2"> <p>與每個描述檔（設定、工作區和視覺化檔案）相關的檔案。 描述檔是由資料集的資料填入。 資料集包括事件資料（「日誌資料」）;此類資料可以由安裝的感測 <span class="wintitle"> 器捕 </span>獲，由網站信標或頁面標籤傳輸，或從資料倉庫輸入。 <span class="keyword"> 可存 </span> 取特定描述檔的前瞻分析使用者可能會使用該描述檔的一組已處理資料，以及該描述檔中定義的工作區和視覺化。 </p> <p>工作區是系統管理或分析的工作區。 工作區可包含多個介面，其中顯示系統效能的不同詳細資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 軟體 </td> 
   <td colname="col2"> <span class="keyword"> 洞察 </span> 軟體更新。 報告軟體更新也會儲存在此處。 </td> 
  </tr> 
 </tbody> 
</table>

## 啟動後建立的目錄和檔案 {#section-ef7408e8fae64454b326ec07453d4628}

下列目錄在註冊後 [!DNL Insight Server] 建立並首次運行：

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
   <td colname="col2"> 處理由 <span class="keyword"> Insight Server產生的資 </span>訊。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 臨時 </td> 
   <td colname="col2"> <p>重新處理和操作期間 <span class="keyword"> Insight Server使用的 </span> 臨時檔案位置。 每個物理驅動器通常有一個文 <span class="filepath"> 件(預設 </span> 命名為temp.db)。 </p> <p> <span class="keyword"> 必須將Insight </span> 伺服器設定為寫入此目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 描圖 </td> 
   <td colname="col2"> 記錄和事件資 <span class="keyword"> 料，關於Insight Server </span>。 對疑難排解非常有用。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用者 </td> 
   <td colname="col2"> 具有伺服器 <span class="keyword"> 設定檔 </span>存取權的已命名(Insight)使用者。 當使用者首次透過 <span class="keyword"> Insight存取Insight Server時，會在「使用者」目錄內建立每個已授權指名 </span> 使用者的 <span class="keyword"> 目錄 </span>。 每個指名用戶的目錄包含與用戶在該 <span class="keyword"> Insight Server上訪問的所有配置檔案以及 </span> 其本地地址檔案相對應的目錄。 </td> 
  </tr> 
 </tbody> 
</table>

