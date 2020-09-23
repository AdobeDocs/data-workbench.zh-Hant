---
description: 感測器在伺服器上使用時，可透過伺服器的API，從任何有效的HTTP要求或回應標題或變數收集事件資料欄位。
solution: Analytics
title: 可延伸欄位
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---


# 可延伸欄位{#extensible-fields}

感測器在伺服器上使用時，可透過伺服器的API，從任何有效的HTTP要求或回應標題或變數收集事件資料欄位。

若要收集此類資料欄位，您必須在設定檔中指定所要的標題欄位 [!DNL txlogd.conf] 或變數 [!DNL Sensor]。

* [請求標題](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [伺服器變數](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## 請求標題 {#section-22766692b45546d8bfc93dbe3bc9368f}

以下語法用於指定要收集的請求標題欄位（例如，主機、接受編碼、保持連結等），位於 [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

收集的資料會記 [!DNL Sensor] 錄到由所建立檔案中名為「cs(RequestHeaderName)」 [!DNL .vsl] 的欄位 [!DNL data workbench server]。 例如，若要從請求標題「主機」收集特定請求標題值，請在中鍵入「LogHeader主機」 [!DNL txlogd.conf]。 資料會記錄在事件資料記錄中的欄位「cs(Host)」。

## 伺服器變數 {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] 可以使用您包含在檔案中的SpecialLogField項目，從回應標題或API可存取的伺服器變數收集資料 [!DNL txlogd.conf] 欄位。 除了「LogHeader」項目以外，您也可以使用「SpecialLogField」項目來收集請求標頭。 請參閱 [請求標題](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)。 請求標題選項仍可用於向後相容性。

以下是在中指定&quot;SpecialLogField&quot;的語法 [!DNL txlogd.conf]:

```
SpecialLogField cs(log field) = serverVariable stage
```

下表包括&quot;SpecialLogField&quot;項的元件說明。

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
   <td colname="col2"> 收集資料記錄在事件資料記錄中的欄位名稱，以及資料工作台伺服器所建立 <span class="filepath"></span> 的。vsl <span class="keyword"> 檔案 </span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>任何可透過伺服器API <span class="wintitle"> 供 </span> Sensor使用的伺服器變數 </p> <p>範例：response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 階段 </td> 
   <td colname="col2"> <p>vys_log或vys_cookie </p> <p>指定階段需要您知道哪些伺服器變數可用於vys_log和vys_cookie。 </p> <p>範例：對於serverVariable response.p3p，您可輸入vys_log。 </p> </td> 
  </tr> 
 </tbody> 
</table>

如需協助設 [!DNL Sensor] 定以收集可擴充的事件資料記錄欄位，請聯絡Adobe諮詢服務。
