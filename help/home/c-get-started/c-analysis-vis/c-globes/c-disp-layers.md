---
description: 「地理位置」設定檔會儲存影像圖層和檔案的集合。
solution: Analytics
title: 顯示圖層
topic: Data workbench
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 顯示圖層{#display-layers}

「地理位置」設定檔會儲存影像圖層和檔案的集合。

在顯示全球時，您可以選擇要針對特定分析任務顯示哪些可用圖層：

* **藍色大理石2公里：** 此圖層顯示地球。 如果未選取此圖層，則不會顯示全球。
* **IP座標：** 此元素點層會根據訪客IP位址，顯示資料集中位置的經緯度。
* **郵遞區號：** 此圖層會根據Adobe提供的美國郵遞區號清單，顯示資料集中位置的經緯度。 查 [!DNL Zip Points.txt] 閱檔案包含要顯示的郵遞區號、緯度和經度資料，而檔 [!DNL Zip Points.layer] 案則包含在全球顯示此資料所需的組態參數。 這兩個檔案都儲存在Profiles\Geography\Maps folder within the Data Workbench server installation directory目錄中。

* ***其他可用圖層名稱：*** 每個層名稱代表儲 [!DNL .layer] 存在Insight Server安裝目錄之Profiles\Geography\Maps folder、Profiles\IP Geo-location\Maps資料夾或Profiles\IP Geo-intelligence\Maps資料夾中的檔案。

>[!NOTE]
>
>若要擁有IP地理位置或IP地理智慧設定檔，您必須分別訂閱IP地理位置或IP地理智慧資料服務。

若要控製圖層的顯示順序，可使用文 [!DNL order.txt] 件。 請參 [閱使用Order.txt檔案自訂功能表](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。

**在全球切換圖層**

* 在視覺化內按一下滑鼠右鍵，然後按一下所要的圖層名稱。 圖層左側的X表示圖層可見。

