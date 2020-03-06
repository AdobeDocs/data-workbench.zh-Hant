---
description: 有關元素點層列的資訊。
solution: Analytics
title: 元素點查閱檔案格式
topic: Data workbench
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 元素點查閱檔案格式{#element-point-lookup-file-format}

有關元素點層列的資訊。

元素點層查閱檔案至少必須包含下列三欄：

* **[!DNL Key]欄：**此欄應包含常用的金鑰資料，這可讓資料工作台伺服器將查閱檔案中的資料連接至資料集中的資料。 該[!DNL Key]欄必須是查閱檔案中的第一欄。 此列中的每一行都標識維的元素。

* **[!DNL Longitude]欄：**此欄應包含欄中每個資料點的經[!DNL Key]度。

* **[!DNL Latitude]欄：**此列應包含列中每個資料點的[!DNL Key]緯度。

* **[!DNL Name]欄：**（可選）。 如果您想要指定每個資料點在地圖上顯示的名稱，您可以在查閱檔案中[!DNL Name]包含一欄。

查閱檔案中 [!DNL Zip Points.txt] 的每一列都包含第一欄中的「郵遞區號」，後面接著經度、緯度和相關的城市名稱。

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

