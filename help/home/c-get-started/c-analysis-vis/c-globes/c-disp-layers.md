---
description: 「地理位置」配置檔案儲存影像層和檔案的集合。
title: 顯示圖層
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# 顯示圖層{#display-layers}

「地理位置」配置檔案儲存影像層和檔案的集合。

當顯示全局時，可以選擇為特定分析任務顯示的可用圖層：

* **藍色大理石2公里：** 此層顯示地球。未選取此層時，地球不可見。
* **IP座標：** 此元素點層會根據訪客IP位址，顯示資料集中位置的經緯度。
* **郵遞區號：** 此層會根據Adobe提供的美國郵遞區號清單，顯示資料集中位置的經緯度。[!DNL Zip Points.txt]查閱檔案包含要顯示的郵遞區號、緯度和經度資料，而[!DNL Zip Points.layer]檔案則包含在全球顯示此資料所需的設定參數。 這兩個檔案都儲存在Profiles\Geography\Maps folder within the Data Workbench server installation directory檔案中。

* ***其他可用的層名稱：*** 每個層名稱代 [!DNL .layer] 表儲存在Profiles\Geography\Maps folder、Profiles\IP Geo-location\Maps資料夾或Profiles\IP Geo-intelligence\Maps資料夾（位於Insight Server安裝目錄內）中的檔案。

>[!NOTE]
>
>若要取得IP地理位置或IP地理情報設定檔，您必須分別訂閱IP地理位置或IP地理情報資料服務。

要控製圖層的顯示順序，可以使用[!DNL order.txt]檔案。 請參閱[使用Order.txt檔案自訂功能表](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。

**切換地球中的圖層**

* 在視覺效果中按一下滑鼠右鍵，然後按一下所需的圖層名稱。 圖層左側的X表示圖層可見。
