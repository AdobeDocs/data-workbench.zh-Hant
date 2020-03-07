---
description: 資料工作台安裝套件中包含的檔案。
title: 安裝包中包含的檔案
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安裝包中包含的檔案{#files-included-in-the-installation-package}

資料工作台安裝套件中包含的檔案。

Insight套件包含下列目錄。

## 程式檔案 {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

預設情況下，Workstation可執&#x200B;**[!DNL Insight.exe]**&#x200B;行檔案()和支援檔案將安裝到此資料夾中。

```
C:\Program Files\Adobe\Adobe Analytics\Data Workbench
```

<table id="table_56BAC85184A04E7680FBB4B36DE73285"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 目錄 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span></b> </td> 
   <td colname="col2"> 資料工作台用戶端可執行檔。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span></b> </td> 
   <td colname="col2"> 設定Appdata資料夾的語 <span class="filepath"> 言和 </span> 路徑。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span></b> </td> 
   <td colname="col2"> <p>資料工作台現在支援輸入法編輯器(IME)做為次要文字輸入程式，可讓您使用浮動文字方塊，從鍵盤輸入國際字元。 資料工作台預設會支援英文，但也可讓您載入其他檔案以支援國際語言，例如虛擬中文鍵盤(Piny IME)。 </p> <p>用戶端應用 <span class="filepath"> 程式需要新的字典 </span>檔案(Insight.zbin)才能支援IME。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> 執行檔，卸載Workstation並刪除檔案。 </td> 
  </tr> 
 </tbody> 
</table>

## AppData檔案 {#section-afddeedf8d29451f996fa46b2dfe932c}

資料檔案(**[!DNL Insight.cfg]**&#x200B;描述檔、憑證、追蹤記錄檔和使用者檔案)預設會儲存為：

```
<filepath>
  C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
</filepath>
```

<table id="table_DBA4DBB54C57409C8EC116C686A08560"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 目錄 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span></b> </td> 
   <td colname="col2"> 資料工作台設定檔案。 定義資料工作台所在的參數。 請參 <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> 閱設定Insight伺服器的連線 </a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> 基 </span> 本 </b> </td> 
   <td colname="col2"> <p>包含資料工作台的程式檔案。 </p> <p> <p>注意： 您不應移除或變更這些檔案。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> 憑證 </span></b> </td> 
   <td colname="col2"> 包含憑證檔案 <span class="filepath"> trust_ca_cert.pem </span>，以及資料工作台的指名用戶數位憑證。 請參 <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> 閱下載和安裝數位憑證 </a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> 設定 </span> </b> </td> 
   <td colname="col2"> 包含用於工作站配置的檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> 地 <span class="filepath"> 理 </span></b> </td> 
   <td colname="col2"> 用於地理視覺化圖形轉換的檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> 描 <span class="filepath"> 圖 </span></b> </td> 
   <td colname="col2"> 從工作站生成的日誌檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> 設 <span class="filepath"> 定檔 </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>、 <i>Predictive Analytics</i> 和其他設定檔設定檔。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> 安裝精靈，可在「軟體／分析」資料夾中安 <b> 裝其他 <span class="filepath"> 用戶端 </span></b> 電腦。 </td> 
  </tr> 
 </tbody> 
</table>

