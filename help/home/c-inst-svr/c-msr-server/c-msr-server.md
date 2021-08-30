---
description: 在規劃和實作系統之前，確定Data Workbench（先前稱為 [!DNL Insight]）伺服器元件的最低需求和建議。
title: 伺服器系統需求
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# 伺服器系統需求{#server-system-requirements}

在規劃和實作系統之前，確定Data Workbench伺服器元件的最低需求和建議。

## DPU需求{#dpu-requirements}

伺服器資料處理單元(DPU)是Data Workbench的主要資料處理元件。 它從Data Workbench監聽網路連接，從檔案伺服器單元(FSU)讀取原始源資料，並使用大量的計算和儲存資源。

### 許可容量 {#section-71850e13783443798b3df9eb22cc63dc}

有關許可證容量資訊，請參閱&#x200B;*Adobe[!DNL Data Workbench (Insight)]服務協定*&#x200B;中的服務說明。

>[!NOTE]
>
>對於Windows 2012伺服器中的&#x200B;*MS System Center Endpoint Protection*，這些執行檔需要添加到&#x200B;***排除的進程：*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]

>


### DPU系統Recommendations和需求 {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe提供符合您業務需求的Data Workbench設計相關建議。 但是，以下准則在選擇作業系統(OS)和硬體時非常有用，因為DPU軟體的優化性質對OS/硬體平台提出了特定要求。

如果單一資料集的容量或速度受限於單一DPU的限制，您可以將其叢集化。 例如，假設您有三份DPU軟體授權復本，可搭配使用以更快速地執行大型資料集。 由於資料平均分配在電腦之間，因此資料集的授權容量會乘以三。 此外，每列的處理速度會比單一DPU快三倍。

為了讓您的DPU投資發揮最佳效能，Adobe建議使用下表所述的下列高效能元件：

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> 必填 </th> 
   <th colname="col3" class="entry"> 建議 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>作業系統  </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td> 
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CPU </p> </td> 
   <td colname="col2"> <p>請參閱建議。 </p> </td> 
   <td colname="col3"> 推薦使用英特爾或AMD的最新一代4核+處理器。 為獲得最佳效能，8核；要在速度和成本之間取得平衡，建議使用4核。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 GB   </p> </td> 
   <td colname="col3"> <p>12 GB   </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>工作資料儲存 </p> </td> 
   <td colname="col2"> <p>總邏輯臨時儲存容量為1 TB+。 </p> <p>對磁碟子系統的低延遲訪問 </p> </td> 
   <td colname="col3"> <p>對於臨時儲存Adobe，建議： </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">（4到8）*（750GB或更高）SATA硬碟（3.5英吋磁碟軸）。 </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">（6到10）*（300GB或更高）SATA硬碟（2.5英吋磁碟軸） </li> 
    </ul> <p>應在JBOD陣列中配置這些內容。 或者，當總磁碟容量超過2TB時，可使用2磁碟RAID1卷陣列。 例如，將6個磁碟配置為3*（2*750GB RAID 1對）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>系統資料儲存 </p> </td> 
   <td colname="col2"> <p>此外，Adobe要求OS、DPU軟體和其他系統軟體的高可用性儲存容量(20GB)。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>群集硬體 </p> </td> 
   <td colname="col2"> <p>請參閱建議。 </p> </td> 
   <td colname="col3"> <p>使用一組同質的伺服器。 在DPU叢集中，最慢的伺服器會降低整個資料集的效能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 群集網路效能 </td> 
   <td colname="col2"> 交換千兆乙太網連接或更高。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### 替代磁碟子系統 {#section-6f984eabe8074759aa9deaf17e3a68b7}

考慮臨時儲存的替代磁碟子系統時，請考慮以下因素和准則：

* DPU對高效能磁碟系統的要求異常高，因此設定不充分的磁碟子系統可能會導致效能瓶頸。
* DPU軟體在一組JBOD磁碟上執行其自身的面向效能的資料條帶化。 請勿使用RAID來提高速度。
* Adobe建議DPU的持續頻寬為400 MB/s以上。
* 平均讀取大小非常高(2MB+)。 因此，15K或10K SAS磁碟的效能通常比SATA磁碟好（或差）一點，成本和容量都大打折扣。
* 避免使用SAN體系結構。 經驗表明，在所需級別執行SAN的成本通常非常高。
* 本地磁碟子系統用作暫存空間 — HDD故障不會永久丟失任何資料，因此請考慮避免成本高昂、速度較慢、高可用性的系統。

### 速度考量 {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe無法提供有關已配置Data Workbench處理資料的速度的保證或表示，因為各種因素影響資料處理速度，包括但不限於以下方面：

* 資料列數
* 資料的維度（欄）數
* 自訂處理步驟的數量和複雜性
* 群集的使用
* 硬體速度

## 檔案伺服器單元要求{#file-server-unit-requirements}

伺服器的檔案服務單元(FSU)是Data Workbench的主要資料儲存和管理元件。 FSU充當檔案伺服器，用於將原始源資料發送到DPU，並在適當時協調DPU的群集。 每個FSU都有權提供最多五(5)個DPU的來源資料。

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> FSU元件 </th> 
   <th colname="col2" class="entry"> 建議 </th> 
   <th colname="col3" class="entry"> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>作業系統、CPU、RAM </p> </td> 
   <td colname="col2"> <p>這些要求與DPU的要求相同。 但是，對於FSU,Adobe建議使用最低要求，而不是遵循建議。 </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>磁碟系統 </p> <p>FSU需要高可用、冗餘的儲存，以容納大量資料。 Adobe會與您合作，決定您的確切需求。 </p> </td> 
   <td colname="col1"> <p>Adobe建議： </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">（12個或更多）*（750GB或更高）RAID 5/6配置中的SATA硬碟。 </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">支援100MB/s+持續頻寬的高效能SAN連接。 </li> 
    </ul> <p>由於FSU保有原始源資料，因此任何損失都是不可恢復的，而Adobe建議定期備份此資料。 </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>網路效能 </p> </td> 
   <td colname="col2"> <p>Adobe需要FSU與DPU之間的千兆位乙太網交換連接，這些FSU與DPU之間需要協同工作。 </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## 感測器要求{#sensor-requirements}

Data Workbench感測器從Web、應用程式和資料收集伺服器收集要傳輸到任何伺服器的事件資料。 [!DNL Sensor’s] 檢測工具可確保對網際網路通道中發生的事件進行一致的準確測量。[!DNL Sensor] 支援Web伺服器軟體和作業系統的多種組合。

### 感測器系統Recommendations {#section-0a981c3a47b644c1a1a56974ba033b9c}

下表說明[!DNL Sensor]的系統建議：

<table id="table_A132E06D6B8146C1B199B82464EA0898"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 功能 </th> 
   <th colname="col2" class="entry"> 建議 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>磁碟儲存 </p> </td> 
   <td colname="col2"> <p>最少512 MB。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>HTTP或其主機的其他伺服器電腦上的<span class="wintitle">感測器</span>必須有32 MB的RAM。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網路效能 </p> </td> 
   <td colname="col2"> <p>與中繼器伺服器或<span class="keyword"> Data Workbench伺服器</span>的1 Mbps或更高網路連線。 <span class="wintitle"> 感測 </span> 器的頻寬通常比一(1)Mbps要少得多。您的Adobe顧問將幫助您估計日常所需的實際頻寬量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網路埠和防火牆 </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> Sensor </span> 使用HTTPS( <span class="keyword"> 通常為連接 </span> 埠443，但此埠可設定)或HTTP（通常為連接埠80，但可設定）連接至Data Workbench伺服器。 </p> <p>駐留在<span class="wintitle">感測器</span>和目標<span class="keyword">資料工作台伺服器</span>或中繼器伺服器之間的任何防火牆上的適當埠，在開始<span class="wintitle">感測器</span>安裝過程之前，應僅在相應的<span class="wintitle">感測器</span>主機與<span class="keyword">資料工作台伺服器</span>或中繼器伺服器之間開啟。 <span class="wintitle"> Sensor </span> 會與Data Workbench伺服器或中繼器伺服器建立單 <span class="keyword"> 向HTTPS </span> 或HTTP連線。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網路管理系統 </p> </td> 
   <td colname="col2"> <p>現有的網路管理系統應監視基礎電腦硬體（例如磁碟空間、網路服務）和網路連接以及Windows事件日誌或UNIX系統日誌的運行狀況。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器時間同步 </p> </td> 
   <td colname="col2"> <p>確保電腦系統時間在承載<span class="wintitle">感測器</span>的每台電腦上持續同步。 <span class="wintitle">感測器</span>監視的Web伺服器應用程式和電腦必須具有同步的系統時間，以便從它們收集的事件資料準確。 請參閱作業系統的文檔，了解與NTP或其他此類時間同步工具持續同步系統時間的步驟。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DNS名稱使用 </p> </td> 
   <td colname="col2"> <p>Adobe建議<span class="wintitle"> Sensor </span>使用DNS名稱（而非IP位址）來解析<span class="keyword"> Data Workbench伺服器</span>或中繼器伺服器的網路位址。 當<span class="wintitle">感測器</span>使用DNS名稱時，需要配置主機Web伺服器的DNS或本地主機檔案，以解析<span class="keyword"> Data Workbench伺服器</span>或中繼器伺服器的名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 支援伺服器軟體 {#section-d6071706539f49d9a861d87b98e6f382}

下表列出[!DNL Sensor]支援的最常見組合：

<table id="table_99EA23BBC1A148B49643F4B5E4341C08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Web伺服器軟體 </th> 
   <th colname="col2" class="entry"> 作業系統  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Apache Server / IBM HTTP Server 2.2 </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003或更高版本；RedHat Enterprise Linux 6.x或更新版本；Sun Solaris 8.x或更高版本；IBM AIX 5.1x或更高版本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apache Server 2.4 </p> </td> 
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x或更新版本 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft IIS </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003或更高版本 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Java應用程式伺服器(Tomcat、JBoss、iPlanet、Weblogic) </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003或更高版本；RedHat Enterprise Linux 6.x或更新版本；Sun Solaris 8.x或更高版本；IBM AIX 5.1x或更高版本。 </p> </td> 
  </tr> 
 </tbody> 
</table>

對於其他伺服器和作業系統組合，請參閱有關可用性的Adobe。 並非所有[!DNL Sensor]功能都適用於Web/應用伺服器和作業系統的所有組合。 有關特定[!DNL Sensor]版本的詳細資訊，請聯繫Adobe支援。

## 報表伺服器需求{#report-server-requirements}

Data Workbench報表伺服器是允許輸出排程報表的元件。 輸出的報表可以是.PNG影像或檔案系統中放置的.XLS電子錶格的形式，也可以是電子郵件形式。 其硬體要求與[Data Workbench客戶端](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=zh-Hant)相同。

[!DNL report server]的要求如下：

* 訪問檔案系統以輸出資料（網路共用或本地驅動器）。
* 訪問配置的SMTP伺服器。
* [!DNL report]伺服器上安裝的Microsoft Excel 2003或更高版本。 如需詳細資訊，請參閱[伺服器端Office自動化考量事項](http://support.microsoft.com/kb/257757) 。

## 網路管理{#network-management}

Adobe建議現有網路管理系統監視Data Workbench平台所依賴的硬體和網路。

此外，Adobe建議監控FSU和DPU的Windows事件記錄，這些記錄會在發生錯誤時寫入。

>[!NOTE]
>
>任何托管日誌檔案的網路儲存系統都需要提供每DPU至少10MB的持續頻寬。

## 資料可用性{#data-availability}

伺服器DPU會將資料處理及重新處理為新或重新整理的資料集，這是正常且必要的作法。

這可能是由於配置更改、資料源更改、硬體更改、不適當的配置、硬體故障、軟體故障、電源故障等。 發生此類處理或重新處理時，所有資料集和系統資料都必須立即可供DPU和FSU元件使用。 如果不遵守這一要求，可能導致系統停機時間顯著且不必要。

## DPU和FSU網路問題{#dpu-and-fsu-network-issues}

使用DPU和FSU網路時應留意的考量事項。

* 對於網路日誌檔案分發，任何托管日誌檔案的網路儲存系統都需要提供每DPU至少10MB的持續頻寬。
* DPU、FSU和Data Workbench之間通過埠80或443上的HTTP或HTTPS雙向通信(預設情況下；埠可以另行配置)。
* Data Workbench[!DNL Sensor(s)]必須能夠（單向）連接到伺服器。
* 若要允許DPU透過SMTP傳送警報訊息，它必須能夠聯絡已設定的SMTP伺服器。
* Adobe建議為FSU和DPU指定網路名稱，如FSU01.CLIENT.COM ，以避免在IP地址更改時進行重新配置。
