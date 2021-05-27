---
description: 有關所需Sensor txlogd.conf參數的資訊。
title: 必要參數
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# 必要參數{#required-parameters}

有關所需Sensor txlogd.conf參數的資訊。

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 在此參數中…… </th> 
   <th colname="col2" class="entry"> 指定分類的... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>唯一標識此<span class="wintitle">感測器</span>的字元字串。 </p> <p> <span class="wintitle"> </span> Sensor會將SensorID附加至傳送至Data Workbench伺服器的每 <span class="keyword"> 個事件記錄</span>。SensorID使來自此Web伺服器的事件資料能夠與其他<span class="wintitle">感測器</span>捕獲的事件資料進行區分。 </p> <p>雖然SensorID可以由字元字串組成，但按慣例，使用Sensor<span class="wintitle"></span>正在捕獲的事件的Web伺服器的名稱。 使用伺服器名稱作為SensorID，可輕鬆判斷分析階段中事件的來源。 它還可確保SensorID在實施中是唯一的。 </p> <p>範例：<span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器地址 </td> 
   <td colname="col2"> <p>此<span class="wintitle">感測器</span>將事件資料傳送到的<span class="keyword"> Data Workbench伺服器</span>的地址。 </p> <p>注意：  <p>在群集環境中工作時，<span class="wintitle">感測器</span>應配置為訪問主<span class="keyword"> Data Workbench伺服器</span>以避免同步問題。 在「Data Workbench」中，您可以使用<span class="wintitle">伺服器管理員</span>中的「相關伺服器」功能表項目，檢視叢集中處理<span class="keyword"> Data Workbench伺服器</span>的相關資訊。 有關<span class="wintitle">伺服器管理器</span>的詳細資訊，請參閱<i><span class="keyword">Data Workbench</span><span class="wintitle">感測器</span>指南</i>。 </p> <p>如果您的Web伺服器可以通過DNS解析伺服器名稱，則可以按名稱指定伺服器的地址。 否則，必須指定伺服器的數值IP地址。 </p> <p>範例：<span class="filepath">伺服器地址10.1.0.7</span>或 </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p><span class="wintitle"> Sensor</span>是否使用HTTP或HTTPS與<span class="keyword"> Data Workbench伺服器</span>通信。 若為HTTPS，則設為「on」，若為HTTP，則設為「off」。 </p> <p>範例：<span class="filepath"></span>上的SSL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器埠 </td> 
   <td colname="col2"> <p><span class="keyword"> Data Workbench伺服器</span>監聽事件資料的連接埠。 </p> <p>範例：<span class="filepath">伺服器埠443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>只有在SSL參數設為「on」時才需要。 </p> <p>此<span class="wintitle"> Sensor</span>將事件資料發送到的<span class="keyword"> Data Workbench伺服器</span>的公用名稱。 </p> <p>您指定的值必須與<span class="keyword"> Data Workbench伺服器</span>授權憑證上顯示的通用名稱完全相符。 </p> <p>範例：<span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>只有在SSL參數設為「on」時才需要。 </p> <p>證書頒發機構(<span class="filepath"> trust_ca_cert.pem</span>)檔案所在的目錄 </p> <p>範例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隊列檔案 </td> 
   <td colname="col2"> <p>運行Internet資訊服務(IIS)5.x或6.x版的Microsoft Windows 2000或2003伺服器電腦上的<span class="wintitle">感測器</span>安裝不需要。 </p> <p>磁碟隊列檔案的完全限定名稱。 </p> <p>雖然可以為此檔案分配任何名稱，但根據慣例，隊列檔案名為<span class="filepath"> VisualSensor.dat</span>。 </p> <p>對於<span class="wintitle"> Sensor</span>在Unix上安裝，可以將此檔案放在任意位置。 在執行Java Web伺服器的Windows上，必須將此檔案放置在與傳輸器相同的目錄中。 對於所有其他Web伺服器，此檔案應位於/var/queue目錄中。 </p> <p>範例：<span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>注意： 請確定您指派此檔案的裝置有足夠的可用空間，以容納所需大小的佇列。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>表示磁碟隊列檔案大小(MB)的整數。 </p> <p>對於在Microsoft Windows上安裝的<span class="wintitle">感測器</span>，隊列檔案本身建立在與發送器相同的目錄中，名為<span class="filepath"> Diskq2000.log</span>。 </p> <p>以下示例將隊列大小設定為200 MB: </p> <p>隊列大小200 </p> <p>以下示例將隊列大小設定為2 GB: </p> <p>隊列大小2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
