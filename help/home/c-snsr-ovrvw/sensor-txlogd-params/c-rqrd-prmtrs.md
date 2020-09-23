---
description: 有關所需感測器txlogd.conf參數的資訊。
solution: Analytics
title: 必要參數
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---


# 必要參數{#required-parameters}

有關所需感測器txlogd.conf參數的資訊。

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 在此參數中…… </th> 
   <th colname="col2" class="entry"> 指定分類的... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 感測器ID </td> 
   <td colname="col2"> <p>唯一標識此感測器的字元 <span class="wintitle"> 串</span>。 </p> <p> <span class="wintitle"> 感測器</span> (Sensor <span class="keyword"> )將SensorID附加到它發送到資料工作台伺服器的每</span>個事件記錄。 SensorID使來自此Web伺服器的事件資料與由其他Sensors捕獲的事件資料能夠 <span class="wintitle"> 區分</span>。 </p> <p>儘管SensorID可以由任意字串組成，但按慣例，SensorID捕獲的事件所使用的Web伺服器 <span class="wintitle"> 名稱</span> 。 使用伺服器名作為SensorID可以在分析階段輕鬆確定事件源。 它還確保SensorID在實施中是唯一的。 </p> <p>範例： <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器位址 </td> 
   <td colname="col2"> <p>此感測器將事 <span class="keyword"> 件資料發送到的</span> 「資料工作台 <span class="wintitle"> 」伺服器的地址</span> 。 </p> <p>注意:  <p>在群集環境中工作時， <span class="wintitle"> Sensor</span> （感測器）應配置為訪問主資料 <span class="keyword"> 工作台伺服器</span> ，以避免同步問題。 在「資料工作台」中，您可以使用「伺服器管理員」中的「相 <span class="keyword"> 關伺服器」功能表項目，來檢視叢集中處理資料工作台伺服器的</span> 相關資訊 <span class="wintitle"></span>。 有關「伺服器管理器」的 <span class="wintitle"> 詳細資訊</span>，請參閱《資料工作台感測器指南 <i><span class="keyword"> 》(Data Workbench</span><span class="wintitle"> Sensor</span> Guide)</i>。 </p> <p>如果您的Web伺服器可以透過DNS解析伺服器名稱，您可以依名稱指定伺服器的位址。 否則，您必須指定伺服器的數值IP位址。 </p> <p>範例： <span class="filepath"> ServerAddress 10.1.0.7</span> 或 </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Sensor <span class="wintitle"></span> whent <span class="keyword"> Sensor</span> with data workbench server using HTTP or HTTPS. 對於HTTPS設為「on」，對於HTTP設為「off」。 </p> <p>範例： <span class="filepath"> SSL on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>資料工作台伺服器監 <span class="keyword"> 聽事件資料</span> ，所在的埠。 </p> <p>範例： <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>僅當SSL參數設為「on」時才需要。 </p> <p>此感測器向其發送事 <span class="keyword"> 件資料的資料工作台</span><span class="wintitle"> 伺服器的公</span> 用名稱。 </p> <p>您指定的值必須與資料工作台伺服器授權憑證上顯示的 <span class="keyword"> 公用名稱</span> 完全相符。 </p> <p>範例： <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>僅當SSL參數設為「on」時才需要。 </p> <p>證書頒發機構(<span class="filepath"> trust_ca_cert.pem</span>)檔案所在的目錄 </p> <p>範例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>在運行Internet Information Service(IIS)5.x或6.x版的Microsoft Windows 2000或2003 Server電腦上安裝感測器時不需要。 <span class="wintitle"></span> </p> <p>磁碟隊列檔案的完全限定名稱。 </p> <p>雖然可以為此檔案指定任何名稱，但按照慣例，隊列檔案名為 <span class="filepath"> VisualSensor.dat</span>。 </p> <p>對於 <span class="wintitle"> Unix上安裝的Sensor</span> ，可以將此檔案放在任意位置。 在運行Java Web伺服器的Windows上，必須將此檔案放置在與發射器相同的目錄中。 對於所有其他Web伺服器，此檔案應位於/var/queue目錄中。 </p> <p>範例： <span class="filepath"> 隊列檔案/var/queue/VisualSensor.dat</span> </p> <p> <p>注意： 請確定您指派此檔案的裝置有足夠的可用空間，以容納所需大小的佇列。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>一個整數，表示磁碟隊列檔案的大小（以MB為單位）。 </p> <p>對於 <span class="wintitle"> Microsoft</span> Windows上的Sensor <span class="filepath"> installations，隊列檔案本身建立在與發射器相同的目錄中，名為</span>Diskq2000.log。 </p> <p>下面的示例將隊列大小設定為200 MB: </p> <p>QueueSize 200 </p> <p>下面的示例將隊列大小設定為2 GB: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>

