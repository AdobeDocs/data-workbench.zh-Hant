---
description: Sensor在伺服器上使用時，可透過伺服器的API，從任何有效的HTTP要求或可用的回應標題或變數中收集事件資料欄位。
title: 可延伸欄位
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# 可延伸欄位{#extensible-fields}

Sensor在伺服器上使用時，可透過伺服器的API，從任何有效的HTTP要求或可用的回應標題或變數中收集事件資料欄位。

要收集此類資料欄位，必須在[!DNL txlogd.conf]配置檔案中為[!DNL Sensor]指定所需的標題欄位或變數。

* [請求標題](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [伺服器變數](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## 請求標題{#section-22766692b45546d8bfc93dbe3bc9368f}

以下是在[!DNL txlogd.conf]中指定要收集的請求標題欄位（例如Host、Accept-Encoding、Keep-Alive等）的語法：

```
LogHeader RequestHeaderName
```

收集的資料由[!DNL Sensor]記錄到[!DNL data workbench server]所建立的[!DNL .vsl]檔案中名為「cs(RequestHeaderName)」的欄位。 例如，若要從請求標題「Host」收集特定請求標題值，您可在[!DNL txlogd.conf]中輸入「LogHeader Host」。 資料會記錄到事件資料記錄中的「cs(Host)」欄位。

## 伺服器變數{#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] 可使用您包含在檔案中的SpecialLogField項目，從回應標題或API可存取的伺服器變數收集資料 [!DNL txlogd.conf] 欄位。除了或之外，您還可以使用「SpecialLogField」條目（而不是「LogHeader」條目）來收集請求標頭。 請參閱[請求標題](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)。 請求標題選項仍可供回溯相容性使用。

以下是在[!DNL txlogd.conf]中指定&quot;SpecialLogField&quot;的語法：

```
SpecialLogField cs(log field) = serverVariable stage
```

下表包括「SpecialLogField」項的元件的說明。

<table id="table_053D5F34D56E4B15A85CA3B4FAD6E1B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元件 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs（log欄位） </td> 
   <td colname="col2"> 收集的資料記錄所在欄位的名稱，以及由<span class="keyword">資料工作台伺服器</span>建立的<span class="filepath"> .vsl </span>檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>任何可通過伺服器的API用於<span class="wintitle">感測器</span>的伺服器變數 </p> <p>範例：response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 階段 </td> 
   <td colname="col2"> <p>vys_log或vys_cookie </p> <p>指定階段需要您知道哪些伺服器變數可用於vys_log和vys_cookie。 </p> <p>範例：對於serverVariable response.p3p，可輸入vys_log。 </p> </td> 
  </tr> 
 </tbody> 
</table>

如需設定[!DNL Sensor]以收集可擴充事件資料記錄欄位的協助，請聯絡Adobe諮詢服務。
