---
description: 歸因設定檔是繼承的、可直接下拉的設定檔。 結合AdobeSC設定檔和Analytics(SC/Insight)資料摘要，可部署設定檔以快速公開數位管道的新歸因模型。
title: 部署歸因設定檔
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
exl-id: 287e1710-7e74-4904-b258-7b811ad484b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 3%

---

# 部署歸因設定檔{#deploying-the-attribution-profile}

{{eol}}

歸因設定檔是繼承的、可直接下拉的設定檔。 結合AdobeSC設定檔和Analytics(SC/Insight)資料摘要，可部署設定檔以快速公開數位管道的新歸因模型。

將歸因設定檔儲存至主要伺服器後，您還需執行兩個額外步驟，將其整合至 [!DNL Profile] 目錄：(1)設定Profile.cfg檔案，並(2)宣告必要欄位。

## 設定Profile.cfg檔案 {#section-7531cb865d994207baba692a6fc842d7}

與所有設定檔一樣，歸因設定檔也需新增至 [!DNL profile.cfg] 檔案。 由于歸因設定檔取決於AdobeSC設定檔，因此AdobeSC設定檔必須先列在設定檔中，再列在歸因設定檔中。

>[!NOTE]
>
>這些步驟需要重新轉換資料集。

1. 開啟 [!DNL profile.cfg] 檔案。 （在中開啟） [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. 如果設定檔案中未列出歸因設定檔，請將其新增至清單。 ![](assets/new_profile_cfg.png)

1. 請確定 **[!UICONTROL Attribution]** 字串列於下方 **[!UICONTROL Adobe SC]** 設定檔字串。

1. 儲存更新的 [!DNL profile.cfg] 檔案，然後從「設定檔管理員」將其儲存至伺服器。

## 聲明必填欄位 {#section-23d4273af0c34b7a85ae3430e2c9350e}

歸因設定檔會取用預先定義的欄位，並透過一系列轉換，透過延伸維度以新的實用方式公開這些欄位。 歸因設定檔要提供最直接的值，須視AdobeSC設定檔中可用的欄位而定。

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 預設變數 </th> 
   <th colname="col2" class="entry"> 欄位名稱和解碼器位置(AdobeSC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 促銷活動 </td> 
   <td colname="col2"> <p>x-campaign, #199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 行銷頻道 </td> 
   <td colname="col2"> <p>x-va_closer_detail,#162 </p> <p>x-va_instance_event, #163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訂購事件 </td> 
   <td colname="col2"> <p>x順序， #206 </p> <p>x-purchaseid, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收入 </td> 
   <td colname="col2"> x-revenue, #205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 單位數 </td> 
   <td colname="col2"> <p>x單元， #204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 確認這些欄位是在用來定義Adobe Analytics資料來源的解碼器群組中宣告。 預設解碼器群組提供於 [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. 確認在 **[!UICONTROL Fields]** 區段 [!DNL SC Fields.cfg] 檔案。 此檔案可位於 [!DNL Dataset\Log Processing\SC Fields.cfg].

## 歸因新增和疑難排解 {#section-168133a8a1a54e1281e532033878d246}

歸因設定檔已新增設定檔， [!DNL 0a_Marketing Channels.cfg]，會複製 [!DNL x-va_closer_detail] 進入名為 [!DNL x-marketing-channel]，當 [!DNL x-va_instance_event] 欄位符合「1」。 兩者 [!DNL x-va_closer_detail] 和 [!DNL x-va_instant_event] 預設會解碼，並在您更新至6.2版時，可用的已安裝套件中從解碼傳遞。

此 [!DNL x-marketing-channel] 欄位隨後會用於名為「行銷管道」的「簡單」維度中。

>[!IMPORTANT]
>
>如果您已移除目前使用的先前未使用欄位，以變更設定檔，您將要確認 [!DNL x-va_closer_detail] 和 [!DNL x-va_instance_event] 欄位正在解碼並傳遞以供使用。

如果欄位遺失，您會收到詳細狀態的訊息：

```
<b>x-va_closer_detail</b> is not available
```

或

```
<b>x-va_instance_event</b> is not available
```
