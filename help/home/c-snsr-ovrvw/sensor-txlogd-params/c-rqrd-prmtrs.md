---
description: 有關所需感測器txlogd.conf參數的資訊。
title: 必要參數
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
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
   <td colname="col2"> <p>唯一標識此<span class="wintitle">感測器</span>的字串。 </p> <p> <span class="wintitle"> SensorID</span> 會將SensorID附加至傳送至資料工作台伺服 <span class="keyword"> 器的每個事件記錄</span>。SensorID使來自此Web伺服器的事件資料與由其他<span class="wintitle">感測器</span>捕獲的事件資料能夠區分開來。 </p> <p>儘管SensorID可由任何字串組成，但按慣例，會使用Web伺服器的名稱，該Web伺服器的事件是<span class="wintitle"> Sensor</span>捕獲的。 使用伺服器名作為SensorID可以在分析階段輕鬆確定事件源。 它還確保SensorID在實施中是唯一的。 </p> <p>範例：<span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器位址 </td> 
   <td colname="col2"> <p>此<span class="wintitle">感測器</span>向其發送事件資料的<span class="keyword">資料工作台伺服器</span>的地址。 </p> <p>注意:  <p>在群集環境中工作時，<span class="wintitle">感測器</span>應配置為訪問主<span class="keyword">資料工作台伺服器</span>以避免同步問題。 在Data Workbench中，您可以使用<span class="wintitle"> Servers Manager</span>中的「相關伺服器」菜單項查看集群中處理<span class="keyword">資料工作台伺服器</span>的資訊。 有關<span class="wintitle">伺服器管理器</span>的詳細資訊，請參閱<i><span class="keyword">Data Workbench</span><span class="wintitle">感測器</span>指南</i>。 </p> <p>如果您的Web伺服器可以透過DNS解析伺服器名稱，您可以依名稱指定伺服器的位址。 否則，您必須指定伺服器的數值IP位址。 </p> <p>範例：<span class="filepath"> ServerAddress 10.1.0.7</span>或 </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p><span class="wintitle">感測器</span>是否使用HTTP或HTTPS與<span class="keyword">資料工作台伺服器</span>通信。 對於HTTPS設為「on」，對於HTTP設為「off」。 </p> <p>範例：<span class="filepath"></span>上的SSL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p><span class="keyword">資料工作台伺服器</span>監聽事件資料的埠。 </p> <p>範例：<span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>僅當SSL參數設為「on」時才需要。 </p> <p>此<span class="wintitle">感測器</span>向其發送事件資料的<span class="keyword">資料工作台伺服器</span>的公用名稱。 </p> <p>您指定的值必須與<span class="keyword">資料工作台伺服器</span>授權憑證上顯示的公用名稱完全相符。 </p> <p>範例：<span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>僅當SSL參數設為「on」時才需要。 </p> <p>證書頒發機構(<span class="filepath"> trust_ca_cert.pem</span>)檔案所在的目錄 </p> <p>範例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>在運行Internet Information Service(IIS)5.x或6.x版的Microsoft Windows 2000或2003 Server電腦上安裝<span class="wintitle">感測器</span>時不需要。 </p> <p>磁碟隊列檔案的完全限定名稱。 </p> <p>雖然可以為此檔案指定任何名稱，但按照慣例，隊列檔案名為<span class="filepath"> VisualSensor.dat</span>。 </p> <p>對於在Unix上安裝的<span class="wintitle">感測器</span>，可以將此檔案放在任意位置。 在運行Java Web伺服器的Windows上，必須將此檔案放置在與發射器相同的目錄中。 對於所有其他Web伺服器，此檔案應位於/var/queue目錄中。 </p> <p>範例：<span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>注意： 請確定您指派此檔案的裝置有足夠的可用空間，以容納所需大小的佇列。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>一個整數，表示磁碟隊列檔案的大小（以MB為單位）。 </p> <p>對於在Microsoft Windows上安裝的<span class="wintitle">感測器</span>，隊列檔案本身建立在與發射器相同的目錄中，名為<span class="filepath"> Diskq2000.log</span>。 </p> <p>下面的示例將隊列大小設定為200 MB: </p> <p>QueueSize 200 </p> <p>下面的示例將隊列大小設定為2 GB: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
