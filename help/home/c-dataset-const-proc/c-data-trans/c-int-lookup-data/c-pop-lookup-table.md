---
description: 如果使用Scorfaled或FlatFileLookup轉換，則查找表將載入記憶體中，並從定義轉換時所指定位置的平面檔案中填充。
title: 填入查閱表格
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
exl-id: e83d9feb-44fe-4fa1-b559-e1f5606637b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 2%

---

# 填入查閱表格{#populating-the-lookup-table}

{{eol}}

如果使用Scorfaled或FlatFileLookup轉換，則查找表將載入記憶體中，並從定義轉換時所指定位置的平面檔案中填充。

指定的平面檔案必須滿足以下要求：

* 檔案中的每一行必須代表查閱表格中的一列。
* 檔案中的列必須以ASCII分隔符分隔。 您可以使用非行尾字元且事件資料本身內未出現的任何字元。 定義轉換時，可指定已使用哪個字元來分隔平面檔案中的列。

如果您使用 [!DNL ODBCLookup] 轉換時，查閱表格會載入記憶體，並從 [!DNL ODBC] 指定的資料庫。 在定義轉換時，您還必須指定Data Workbench伺服器用來建立與資料庫連線的資料來源、使用者名稱及密碼。

>[!NOTE]
>
>Data Workbench伺服器最初開始建立資料集時，會載入查閱表格。 建立後，就不會變更查閱檔案。 如果更改平面檔案或 [!DNL ODBC] 表格（用於轉換階段），您需要重新轉換整個資料集。 如果您變更的是記錄處理階段期間使用的一般檔案，新查閱資料會套用至輸入資料集的所有新記錄，但變更不會回溯套用。
