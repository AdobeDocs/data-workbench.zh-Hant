---
description: 有關Sensor UNIX檔案權限的資訊，如收集器模組、傳輸器進程、配置檔案等。
title: Sensor UNIX 檔案權限
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
exl-id: 07cbc7df-c628-437d-9ca1-b006da8de242
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 5%

---

# Sensor UNIX 檔案權限{#sensor-unix-file-permissions}

{{eol}}

有關Sensor UNIX檔案權限的資訊，如收集器模組、傳輸器進程、配置檔案等。

## 收集器模組 {#section-49c855baece24c4695184bfcbeeddebf}

<table id="table_0B972ABD2A5342CA8A6FE80EB666298A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 品質 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>檔案名稱 </p> </td> 
   <td colname="col2"> <p>mod_visual_sciences.so(在Apache Web伺服器和IBM HTTP伺服器上) </p> <p>libvisual_sciences.so和J2EECollector.jar（在J2EE應用程式伺服器上） </p> <p>aol_visual_sciences.so（在AOL Web伺服器上） </p> <p>saf_visual_sciences.so（在Sun Java Web伺服器上） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>預設權限 </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x(IBM HTTP和Apache 1.3.x) </p> <p>rwx rwx r-x(Apache 2.0.x) </p> <p>rwx —x —x（J2EE、AOL和Sun Java Web伺服器） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>閱讀者 </p> </td> 
   <td colname="col2"> <p>Web伺服器，有時以根使用者身分執行，但更常在特定使用者帳戶下執行 </p> <p>如果Web伺服器在非根帳戶下運行，則此檔案的權限必須允許該帳戶讀取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>以 </p> </td> 
   <td colname="col2"> <p>Web伺服器中的子進程 </p> <p>子進程在Web伺服器配置中指定的用戶帳戶下運行。 在許多伺服器上，這是一個特殊帳戶，其特權非常有限，稱為「無人」 — 但並非所有Web伺服器都使用此帳戶。 檢查Web伺服器的配置檔案，以確定設定了哪個用戶帳戶。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>讀取 </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>diskQueue檔案 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 寫入 </td> 
   <td colname="col2"> diskQueue檔案 </td> 
  </tr> 
 </tbody> 
</table>

## 傳送器程式 {#section-8af432472e9d4bd9a42270bf27adf33a}

<table id="table_3028CC9640D54016BD8CA7F9CAA34280"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 品質 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 檔案名稱 </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>預設權限 </p> </td> 
   <td colname="col2"> <p>rw- r— r—(IBM HTTP、AOL和Sun Java Web伺服器) </p> <p>rw-rw- r — （Apache Web伺服器和J2EE應用程式伺服器） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 閱讀者 </td> 
   <td colname="col2"> 發射機程式 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 寫入者 </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## 組態檔 {#section-341d85f2abf34a69970a0ff91b7e9123}

<table id="table_79AC614F5435443CB3CFB457B8375704"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 品質 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 檔案名稱 </td> 
   <td colname="col2"> txlogd.conf </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>預設權限 </p> </td> 
   <td colname="col2"> <p>rw- r— r—(IBM HTTP、AOL和Sun Java Web伺服器) </p> <p>rw-rw- r — （Apache Web伺服器和J2EE應用程式伺服器） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 閱讀者 </td> 
   <td colname="col2"> <p>收集器模組 </p> <p>發射機程式 </p> <p>負責安裝、配置和維護Sensor的管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 寫入者 </td> 
   <td colname="col2"> 負責安裝、配置和維護Sensor的管理員 </td> 
  </tr> 
 </tbody> 
</table>

## 證書頒發機構檔案 {#section-2818dff887b8456992bdc589fd8510f3}

<table id="table_ED8BEEEFA91245C3A6645D27B148A5A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 品質 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 檔案名稱 </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>預設權限 </p> </td> 
   <td colname="col2"> <p>rw- r— r—(IBM HTTP、AOL和Sun Java Web伺服器) </p> <p>rw-rw- r — （Apache Web伺服器和J2EE應用程式伺服器） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 閱讀者 </td> 
   <td colname="col2"> 發射機程式 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 寫入者 </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## 磁碟隊列 {#section-0407c52744de41af867d0b7933a69256}

<table id="table_35DB32228E7443FF90BE24AB14CBE54B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 品質 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 檔案名稱 </td> 
   <td colname="col2"> 用戶定義 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預設權限 </td> 
   <td colname="col2"> rw-rw-rw — （所有伺服器類型） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>閱讀者 </p> </td> 
   <td colname="col2"> <p>收集器模組 </p> <p>發射機程式 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>寫入者 </p> </td> 
   <td colname="col2"> <p>收集器模組 </p> <p>發射機程式 </p> </td> 
  </tr> 
 </tbody> 
</table>
