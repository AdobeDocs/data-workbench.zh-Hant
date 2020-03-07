---
description: 設定時間維度以正確顯示地區設定。
title: 本地化時間維
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# 本地化時間維{#localizing-time-dimensions}

設定時間維度以正確顯示地區設定。

您可以根據檔案中的地區設定來設定時間維度的顯示格式 **[!DNL Standard Time Dimensions.cfg]** (依預設位於 **[!DNL Server/Profiles/`<my profile>`/Dataset/Transformation/Time/Standard Time Dimensions.cfg]**)。

例如，在北美洲，您可以將日期2015年5月3日表示為5/3/15或 **`%m/%d/%y`**。 然而，在世界其他地區，這可以解讀為 `%d/%m/%y`2015年3月5日，因為價值觀模稜兩可。 為避免這種情況，管理員可能希望更改顯示的格式，以符合區域設定中用戶的期望。

## 1.覆寫標準時間維度。cfg中的預設時間維度 {#section-7d0b24657bef4b15abb3cbea66cb617f}

要啟用此功能，管理員必須通過編輯現有時間維或通過使用其他參數建立新時間維來覆蓋預設值。

下面是修改時間維的示例。

「 **周** 」、「小時」、「日」、「月」和「小時」的「格式」值在範例中設定為預設值。

>[!NOTE]
>
>如果省略這些行，資料工作台的行為不會變更，而且維度會使用預設值進行編譯。

```
Transformation Include = TransformationInclude:  
  Extended Dimensions = vector: 1 items 
    0 = TimeDimensions:  
      Comments = Comment: 0 items 
      Dimensions = map:  
        Day = string: Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Hour of Day = string: Hour of Day 
        Month = string: Month 
        Week = string: Week 
      Hidden = bool: false 
      Input Time (1970 epoch) = string: x-unixtime 
      Week Format = string:  
  %m/%d/%y
      Hour Format = string:  
  %x %H:%M 
      Day Format = string:  
  %x
      Month Format = string:  
  %b '%y
      Hour Of Day Format = string:  
  %#H:%M
      Name = string: Visit Time 
      Parent = string: Visit 
      Week Start Day = string: Mon 
  Transformations = vector: 0 items
```

![](assets/6_4_time_format.png)

## 2.設定meta.cfg檔案 {#section-5e077d3298dd48fda7f7bb16af9ea00c}

此外，套件管理員必須將這些參數及其預設值新增至描述檔的檔 **[!DNL meta.cfg]** 案。 這允許從工作站進行編輯。

這是一段節錄，來自一個配置的 **[!DNL meta.cfg]** 檔案。

```
dimensions = vector: 6 items 
  0 = Template: 
    ...
  ...
  5 = Template: 
    name = string: Time Dimensions 
    value = TimeDimensions: 
      Name = string:  
      Comments = Comment: 0 items 
      Hidden = bool: false 
       
  Week Format = string: %d/%m/%y 
       Hour Format = string: %x %H:%M 
       Day Format = string: %x 
       Month Format = string: %b '%y 
       Hour Of Day Format = string: %#H:%M</b> 
      Input Time (1970 epoch) = string:  
      Parent = string:  
      Week Start Day = string: Mon 
      Dimensions = map: 
        Hour of Day = string: Hour of Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Day = string: Day 
        Week = string: Week 
        Month = string: Month
```

以下是工作站中的 **[!DNL meta.cfg]** 檔案示例：

![](assets/dwb_time_format.png)

然後，管理員可以進入「檔案管理器」 **，開啟配置時間維的檔案(如****[!DNL Standard Time Dimensions.cfg]**)，並在工作站中使用它們進行編輯。
