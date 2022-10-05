---
description: Sensor在伺服器上使用時，可透過伺服器的API，從任何有效的HTTP要求或可用的回應標題或變數中收集事件資料欄位。
title: 可延伸欄位
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 2%

---

# 可延伸欄位{#extensible-fields}

{{eol}}

Sensor在伺服器上使用時，可透過伺服器的API，從任何有效的HTTP要求或可用的回應標題或變數中收集事件資料欄位。

若要收集這類資料欄位，您必須在 [!DNL txlogd.conf] 配置檔案 [!DNL Sensor].

* [請求標題](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [伺服器變數](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## 請求標題 {#section-22766692b45546d8bfc93dbe3bc9368f}

以下是指定要收集之要求標題欄位（例如Host、Accept-Encoding、Keep-Alive等）的語法，位於 [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

收集的資料由 [!DNL Sensor] 填入 [!DNL .vsl] 由建立的檔案 [!DNL data workbench server]. 例如，若要從請求標題「Host」中收集特定請求標題值，您可在 [!DNL txlogd.conf]. 資料會記錄到事件資料記錄中的「cs(Host)」欄位。

## 伺服器變數 {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] 可使用您包含在 [!DNL txlogd.conf] 檔案。 除了或之外，您還可以使用「SpecialLogField」條目（而不是「LogHeader」條目）來收集請求標頭。 請參閱 [請求標題](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). 請求標題選項仍可供回溯相容性使用。

以下是指定 [!DNL txlogd.conf]:

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
   <td colname="col2"> 收集的資料記錄所在欄位的名稱，以及 <span class="filepath"> .vsl </span> 由建立的檔案 <span class="keyword"> data workbench伺服器 </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>任何可用於 <span class="wintitle"> 感測器 </span> 透過伺服器的API </p> <p>範例：response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>vys_log或vys_cookie </p> <p>指定階段需要您知道哪些伺服器變數可用於vys_log和vys_cookie。 </p> <p>範例：對於serverVariable response.p3p，可輸入vys_log。 </p> </td> 
  </tr> 
 </tbody> 
</table>

如需協助設定 [!DNL Sensor] 若要收集可擴充的事件資料記錄欄位，請聯絡Adobe諮詢服務。
