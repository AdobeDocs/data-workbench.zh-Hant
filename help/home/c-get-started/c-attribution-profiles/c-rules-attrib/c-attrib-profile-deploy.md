---
description: Attribution描述檔是繼承的、現成可下載的描述檔。 結合Adobe SC設定檔與Analytics(SC/Insight)資料饋送，可部署該設定檔，以快速跨數位通道公開新的歸因模型。
title: 部署歸因設定檔
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 部署歸因設定檔{#deploying-the-attribution-profile}

Attribution描述檔是繼承的、現成可下載的描述檔。 結合Adobe SC設定檔與Analytics(SC/Insight)資料饋送，可部署該設定檔，以快速跨數位通道公開新的歸因模型。

將Attribution描述檔儲存至主要伺服器後，需要另外兩個步驟將其整合至目錄內的目前描述檔 [!DNL Profile] 中：(1)設定Profile.cfg檔案，並(2)宣告必填欄位。

## 設定Profile.cfg檔案 {#section-7531cb865d994207baba692a6fc842d7}

和所有描述檔一樣，Attribution描述檔也需要新增至 [!DNL profile.cfg] 檔案。 由於「歸因」描述檔取決於Adobe SC描述檔，因此Adobe SC描述檔必須先列在設定檔中，再列在「歸因」描述檔之前。

>[!NOTE]
>
>這些步驟需要重新轉換資料集。

1. 在自訂 [!DNL profile.cfg] 描述檔資料夾中開啟檔案。 (在中開啟 [!DNL server\Profiles\(custom profile name)\profile.cfg]。

1. 如果配置檔案中未列出Attribution配置檔案，請將其添加到清單中。 ![](assets/new_profile_cfg.png)

1. 請確定字 **[!UICONTROL Attribution]** 串列在描述檔字串 **[!UICONTROL Adobe SC]** 下方。

1. 儲存更新檔 [!DNL profile.cfg] 案，然後從「描述檔管理員」將它儲存至伺服器。

## 宣告必填欄位 {#section-23d4273af0c34b7a85ae3430e2c9350e}

「歸因」設定檔會取用預先定義的欄位，而一系列轉換會透過延伸維度以新的有用方式呈現這些欄位。 Attribution描述檔要提供最直接的值，取決於Adobe SC描述檔中的欄位。

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 預設變數 </th> 
   <th colname="col2" class="entry"> 欄位名稱與解碼器位置(Adobe SC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 促銷活動 </td> 
   <td colname="col2"> <p>x-campaign,#199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 行銷管道 </td> 
   <td colname="col2"> <p>x-va_closer_detail, #162 </p> <p>x-va_instance_event, #163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訂購事件 </td> 
   <td colname="col2"> <p>x訂單，#206 </p> <p>x-purchaseid, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收入 </td> 
   <td colname="col2"> x-revenue, #205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 件數 </td> 
   <td colname="col2"> <p>x-units,#204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 確認這些欄位已宣告於用來定義Adobe Analytics資料來源的「解碼器群組」中。 預設解碼器群組提供於下 [!DNL Dataset\Log Procesing\Decoding Instructions.cfg]。
1. 驗證這些欄位是否在檔案 **[!UICONTROL Fields]** 的部分中聲 [!DNL SC Fields.cfg] 明。 此檔案可位於下 [!DNL Dataset\Log Processing\SC Fields.cfg]。

## 歸因新增與疑難排解 {#section-168133a8a1a54e1281e532033878d246}

Attribution描述檔新增了設定檔 [!DNL 0a_Marketing Channels.cfg]，當欄位符合「1」 [!DNL x-va_closer_detail] 時，會將值複製到名為 [!DNL x-marketing-channel]「 [!DNL x-va_instance_event] 新欄位」的欄位中。 預設 [!DNL x-va_closer_detail] 會對 [!DNL x-va_instant_event] 和進行解碼，並在您更新至6.2版時，從已安裝的封裝中傳遞解碼。

然後 [!DNL x-marketing-channel] 在稱為行銷渠道的簡單維度中使用欄位。

>[!IMPORTANT]
>
>如果您已移除目前使用的先前未使用的欄位，以變更個人檔案，您會想確認 [!DNL x-va_closer_detail] 和 [!DNL x-va_instance_event] 欄位已解碼並傳遞給使用者。

如果欄位遺失，您會收到詳細狀態的訊息：

```
<b>x-va_closer_detail</b> is not available
```

或

```
<b>x-va_instance_event</b> is not available
```

