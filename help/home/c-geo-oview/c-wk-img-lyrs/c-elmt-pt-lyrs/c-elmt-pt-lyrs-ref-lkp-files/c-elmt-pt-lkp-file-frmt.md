---
description: 有關元素點層列的資訊。
title: 元素點查閱檔案格式
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 6%

---

# 元素點查閱檔案格式{#element-point-lookup-file-format}

有關元素點層列的資訊。

元素點層查閱檔案至少必須包含下列三欄：

* **[!DNL Key]欄：** 此欄應包含通用索引鍵資料，這可讓Data Workbench伺服器將查詢檔案中的資料連線至資料集中的資料。[!DNL Key]欄必須是查閱檔案中的第一欄。 此欄中的每一列都代表維度的元素。

* **[!DNL Longitude]欄：** 此欄應包含欄中每個資料點的經 [!DNL Key] 度。

* **[!DNL Latitude]column:** 此欄應包含欄中每個資料點的 [!DNL Key] 緯度。

* **[!DNL Name]欄：** （選用）。如果要指定要在地圖上顯示每個資料點的名稱，您可以在查閱檔案中加入[!DNL Name]欄。

[!DNL Zip Points.txt]查閱檔案中的每一列都包含第一欄中的郵遞區號，後面接著經度、緯度以及相關的城市名稱。

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
