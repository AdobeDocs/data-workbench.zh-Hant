---
description: Data Workbench安裝套件中包含的檔案。
title: 安裝套件中包含的檔案
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
exl-id: 086fb49c-d492-4670-938b-7ede70a7cd16
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 5%

---

# 安裝套件中包含的檔案{#files-included-in-the-installation-package}

{{eol}}

Data Workbench安裝套件中包含的檔案。

Insight套件包含下列目錄。

## 程式檔案 {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

工作站執行檔(**[!DNL Insight.exe]**)和支援檔案預設會安裝至此資料夾。

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
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span> </b> </td> 
   <td colname="col2"> Data Workbench客戶端執行檔。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span> </b> </td> 
   <td colname="col2"> 設定語言和 <span class="filepath"> Appdata </span> 檔案夾。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span> </b> </td> 
   <td colname="col2"> <p>Data Workbench現在支援輸入法編輯器(IME)作為次要文字輸入程式，可讓您使用浮動文字方塊從鍵盤輸入國際字元。 Data Workbench預設會支援英文，但也可讓您載入其他檔案以支援國際語言，例如虛擬中文鍵盤（拼音輸入法）。 </p> <p>新的字典檔案 <span class="filepath"> (Insight.zbin </span>)是客戶端應用程式支援IME的必需項。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> 可執行檔，用於卸載Workstation和刪除檔案。 </td> 
  </tr> 
 </tbody> 
</table>

## AppData檔案 {#section-afddeedf8d29451f996fa46b2dfe932c}

資料檔案(**[!DNL Insight.cfg]**、設定檔、憑證、追蹤記錄檔和使用者檔案)會依預設儲存為：

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
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span> </b> </td> 
   <td colname="col2"> Data Workbench配置檔案。 定義Data Workbench運作的參數。 請參閱 <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> 設定與Insight Server的連線 </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> 基 </span> </b> </td> 
   <td colname="col2"> <p>包含要Data Workbench的程式檔案。 </p> <p> <p>注意：您不應移除或更改任何這些檔案。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> 憑證 </span> </b> </td> 
   <td colname="col2"> 包含憑證檔案， <span class="filepath"> trust_ca_cert.pem </span>，以及指名的使用者數位憑證以進行Data Workbench。 請參閱 <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> 下載和安裝數位憑證 </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> 設定 </span> </b> </td> 
   <td colname="col2"> 包含用於工作站配置的檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Geography </span></b> </td> 
   <td colname="col2"> 地理視覺效果的圖形轉譯檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Trace </span></b> </td> 
   <td colname="col2"> 從工作站產生的記錄檔。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> 設定檔 </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>, <i>預測性分析</i> 和其他設定檔組態檔。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> 安裝嚮導，以在 <b> <span class="filepath"> 軟體/分析 </span></b> 檔案夾。 </td> 
  </tr> 
 </tbody> 
</table>
