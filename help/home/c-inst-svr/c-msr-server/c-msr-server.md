---
description: 在規劃和實作系統之前，先識別資料工作台（先前稱為[!DNL Insight]）伺服器元件的最低需求和建議。
title: 伺服器系統需求
uuid: c4487c76-03b9-4755-893b-555d451b1e69
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 伺服器系統需求{#server-system-requirements}

在規劃和實作系統之前，先識別資料工作台伺服器元件的最低需求和建議。

## DPU需求{#dpu-requirements}

伺服器資料處理單元(DPU)是資料工作台的主要資料處理元件。 它會監聽來自資料工作台的網路連線，從檔案伺服器單元(FSU)讀取原始來源資料，並使用大量的計算和儲存資源。

### 授權容量 {#section-71850e13783443798b3df9eb22cc63dc}

如需授權容量資訊，請參閱 *Adobe服務[!DNL Data Workbench (Insight)]合約中的「服務說明* 」。

>[!NOTE]
>
>對於 *Windows 2012伺服器中的MS System Center端點保護* ，這些執行檔需要添加到排除的 ***進程中：*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]
>



### DPU系統建議與需求 {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe針對符合您業務需求的資料工作台設計提供建議。 但是，在選擇作業系統(OS)和硬體時，以下准則非常有用，因為DPU軟體的優化性對OS/硬體平台有特定要求。

如果單一資料集受單一DPU的容量或速度限制，您可以將它們叢集。 例如，假設您有三份DPU軟體的授權副本，可搭配使用，以更快速地執行大型資料集。 當資料平均分割在機器之間時，資料集的授權容量會乘以三。 此外，每列的處理速度會比單一DPU快3倍。

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
   <td colname="col3"> 建議使用Intel或AMD的最新一代4核以上處理器。 為獲得最佳效能，8核；為了在速度與成本之間取捨，建議使用4核。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 GB </p> </td> 
   <td colname="col3"> <p>12 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>工作資料儲存 </p> </td> 
   <td colname="col2"> <p>總邏輯溫度儲存超過1TB。 </p> <p>對磁碟子系統的低延遲訪問 </p> </td> 
   <td colname="col3"> <p>對於暫存器，Adobe建議您以下任一方式： </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">（4到8個）*（750GB或更高）SATA硬碟（3.5英吋主軸） </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">（6到10）*（300GB或更高）SATA硬碟（2.5英吋主軸） </li> 
    </ul> <p>應在JBOD陣列中配置這些。 或者，當總磁碟容量超過2TB時，可以使用2磁碟RAID1卷的陣列。 例如，將6個磁碟配置為3*（2*750GB RAID 1對）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>系統資料儲存 </p> </td> 
   <td colname="col2"> <p>此外，Adobe需要適當大小(20GB)的高可用性儲存，以用於作業系統、DPU軟體和其他系統軟體。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>群集硬體 </p> </td> 
   <td colname="col2"> <p>請參閱建議。 </p> </td> 
   <td colname="col3"> <p>使用同構的伺服器集。 在DPU叢集中，最慢的伺服器會降低整個資料集的效能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 群集網路效能 </td> 
   <td colname="col2"> 交換千兆位乙太網連接或更高。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### 備用磁碟子系統 {#section-6f984eabe8074759aa9deaf17e3a68b7}

在考慮用於臨時儲存的替代磁碟子系統時，請考慮以下因素和准則：

* DPU對高效能磁碟系統的要求異常高，因此設定不足的磁碟子系統可能會導致效能瓶頸。
* DPU軟體在一組JBOD磁碟上執行其自己的面向效能的資料條帶化。 切勿使用RAID來提高速度。
* Adobe建議DPU的磁碟持續頻寬總計超過400 MB/s。
* 平均讀取大小非常高（2MB以上）。 因此，15K或10K SAS磁碟的效能通常比SATA磁碟更好（或更差），而且成本和容量都大大降低。
* 避免使用SAN體系結構。 經驗表明，使SAN在所需級別上執行的成本通常非常高。
* 本地磁碟子系統用作暫存空間——沒有資料會永久丟失，因此請考慮避免昂貴、速度較慢的高可用性系統。

### 速度考量 {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe無法提供有關設定資料工作台處理資料的速度的保證或表示，因為各種因素會影響資料處理速度，包括但不限於：

* 資料列數
* 資料的維度（欄）數
* 自訂處理步驟的數量和複雜性
* 使用叢集
* 硬體速度

## 檔案伺服器單元要求{#file-server-unit-requirements}

伺服器的檔案伺服單元(FSU)是資料工作台的主要資料儲存與管理元件。 FSU充當檔案伺服器，用於將原始源資料發送到DPU，並且在適當時協調DPU的群集。 每個FSU都可提供最多五(5)個DPU的來源資料。

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
   <td colname="col2"> <p>這些要求與DPU的要求相同。 不過，對於FSU,Adobe建議使用最低要求，而非遵循建議。 </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>磁碟系統 </p> <p>FSU需要高可用、冗餘的儲存來儲存大量資料。 Adobe會與您合作，確定您的確切需求。 </p> </td> 
   <td colname="col1"> <p>Adobe建議： </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">（12個或更多）*（750GB或更大）RAID 5/6配置中的SATA硬碟。 </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">支援100MB/s以上持續頻寬的高效能SAN連接。 </li> 
    </ul> <p>由於FSU保有原始來源資料，因此任何損失都無法復原，Adobe建議定期備份此資料。 </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>網路效能 </p> </td> 
   <td colname="col2"> <p>Adobe需要FSU和DPU之間的交換千兆位乙太網連線，而FSU和DPU之間必須搭配運作。 </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## 感測器要求{#sensor-requirements}

資料工作台感測器會從網路、應用程式和資料收集伺服器收集事件資料，並傳送至任何伺服器。 [!DNL Sensor’s] 此工具可確保對您網際網路通道中發生的事件進行一致精確的測量。 [!DNL Sensor] 支援許多Web伺服器軟體和作業系統的組合。

### 感測器系統建議 {#section-0a981c3a47b644c1a1a56974ba033b9c}

下表說明下列的系統建議 [!DNL Sensor]:

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
   <td colname="col2"> <p>HTTP或其主機的其他伺服器 <span class="wintitle"> 電 </span> 腦上的感測器必須有32 MB的記憶體。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網路效能 </p> </td> 
   <td colname="col2"> <p>1 Mbps或更高的網路連線至中繼器伺服器或資 <span class="keyword"> 料工作台伺服 </span>器。 <span class="wintitle"> 感測 </span> 器的頻寬消耗通常比一(1)Mbps少得多。 您的Adobe顧問將協助您估計日常所需的實際頻寬量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網路埠和防火牆 </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> 感測 </span> 器使用HTTPS（通常是埠443，但是這是可配置的）或HTTP（通常是埠80，但是可配置的）連 <span class="keyword"></span> 接到資料工作台伺服器。 </p> <p>在開始安裝感測器之前，只應在相應的感測器托管電腦和感測器工作台或中繼器伺服器之間開啟位於感測器和目標資料工作台伺服器之間的防火牆上的適當埠。 <span class="wintitle"> Sensor主管電腦和 </span><span class="keyword"></span><span class="wintitle"></span><span class="keyword"></span><span class="wintitle"></span> Repeater伺服器或中繼器資料伺服器之間應開始安裝感測器。 <span class="wintitle"> 感測 </span> 器與資料工作台伺服器或中繼器伺服器建立單向HTTPS <span class="keyword"> 或HTTP </span> 連線。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網路管理系統 </p> </td> 
   <td colname="col2"> <p>現有的網路管理系統應監視底層電腦硬體（如磁碟空間、網路服務）和網路連接狀況，以及Windows事件日誌或UNIX系統日誌。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器時間同步 </p> </td> 
   <td colname="col2"> <p>確保托管感測器的每台電腦的電腦系統時間持續 <span class="wintitle"> 同步 </span>。 感測器監視的Web伺服器應用程式和計算 <span class="wintitle"> 機 </span> 必須具有同步的系統時間，才能使從它們收集的事件資料準確。 有關使系統時間與NTP或其他此類時間同步設施進行持續同步的步驟，請參閱作業系統文檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DNS名稱使用 </p> </td> 
   <td colname="col2"> <p>Adobe建議 <span class="wintitle"> Sensors </span> 使用DNS名稱（而非IP位址）來解析資料工作台伺服器或中繼器伺服器 <span class="keyword"> 的網 </span> 路位址。 當感測 <span class="wintitle"> 器使 </span> 用DNS名稱時，主機Web伺服器的DNS或本地主機檔案需要配置以解析資料工作台伺服器或中繼器伺服器 <span class="keyword"></span> 的名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 支援伺服器軟體 {#section-d6071706539f49d9a861d87b98e6f382}

下表列出最常支援的組合 [!DNL Sensor] :

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
   <td colname="col2"> <p>Microsoft Windows Server 2003或更高版本；RedHat Enterprise Linux 6.x或更新版本；Sun Solaris 8.x或更新版本；IBM AIX 5.1x或更新版本。 </p> </td> 
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
   <td colname="col2"> <p>Microsoft Windows Server 2003或更高版本；RedHat Enterprise Linux 6.x或更新版本；Sun Solaris 8.x或更新版本；IBM AIX 5.1x或更新版本。 </p> </td> 
  </tr> 
 </tbody> 
</table>

若需其他伺服器和作業系統組合，請洽詢Adobe有關可用性的資訊。 Web/應用程式伺 [!DNL Sensor] 服器與作業系統的組合併非所有功能都可使用。 如需特定版本的詳細 [!DNL Sensor] 資訊，請聯絡Adobe支援。

## 報表伺服器需求{#report-server-requirements}

資料工作台報表伺服器是允許輸出排程報表的元件。 輸出的報表可以是。PNG影像或。XLS試算表格式，也可以是電子郵件格式。 其硬體需求與資料工作台 [用戶端相同](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html)。

下列要求適用 [!DNL report server]:

* 存取檔案系統以輸出資料（網路共用或本機磁碟機）。
* 訪問已配置的SMTP伺服器。
* 伺服器上已安裝Microsoft Excel 2003或更 [!DNL report] 高版本。 如需 [詳細資訊，請參閱Office伺服器端自動化注意事項](http://support.microsoft.com/kb/257757) 。

## 網路管理{#network-management}

Adobe建議現有的網路管理系統監控資料工作台平台所仰賴的硬體和網路。

此外，Adobe建議監控FSU和DPU的Windows事件記錄檔，這些記錄檔會在發生錯誤時寫入。

>[!NOTE]
>
>任何托管日誌檔案的網路儲存系統都需要為每DPU提供至少10MB的持續頻寬。

## 資料可用性{#data-availability}

伺服器DPU將資料處理並重新處理至新資料集或重新整理的資料集，是正常且必要的做法。

這可能是由於配置更改、資料源更改、硬體更改、不適當的配置、硬體故障、軟體故障、電源故障等原因造成的。 當此類處理或重新處理髮生時，所有資料集和系統資料必須立即可供DPU和FSU元件使用。 如果不遵守這一要求，可能導致系統停機時間顯著而不必要。

## DPU和FSU網路問題{#dpu-and-fsu-network-issues}

使用DPU和FSU網路時應注意的事項。

* 對於網路日誌檔案分發，任何托管日誌檔案的網路儲存系統都必須提供每DPU至少10MB的持續頻寬。
* DPU、FSU和資料工作台在連接埠80或443上透過HTTP或HTTPS雙向通訊(預設為；埠可以選擇配置)。
* 資料工 [!DNL Sensor(s)] 作台必須能夠（單向）連線至伺服器。
* 要允許DPU通過SMTP發送警報消息，它必須能夠聯繫已配置的SMTP伺服器。
* Adobe建議為FSU和DPU指定網路名稱，例如FSU01.CLIENT.COM，以避免在IP位址變更時進行重新配置。