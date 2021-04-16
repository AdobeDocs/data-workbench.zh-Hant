---
description: 如果您訂閱任一資料服務，則必須定期更新Adobe提供的資料服務檔案。
title: 更新資料服務檔案
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# 更新資料服務檔案{#updating-data-service-files}

如果您訂閱任一資料服務，則必須定期更新Adobe提供的資料服務檔案。

若要這麼做，您必須擁有資料工作台伺服器上檔案的存取權。

要載入[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]資料檔案，必須完成以下過程。

## 更換資料檔案{#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. 在資料工作台的[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟[!DNL Servers Manager]工作區。

1. 在[!DNL Servers Manager]窗口中，按一下右鍵要載入檔案的資料工作台伺服器的表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。

1. 在[!DNL Server Files Manager]中，按一下右鍵&#x200B;**[!UICONTROL Lookups\IP Geo-location]**&#x200B;或&#x200B;**[!UICONTROL Lookups\IP Geo-intelligence]**&#x200B;的&#x200B;**[!UICONTROL Temp]**&#x200B;列，然後按一下&#x200B;**[!UICONTROL Open]** > ***[!UICONTROL folder]***。

1. 將Adobe提供的[!DNL .bin]資料檔案複製至Lookups\IP Geo-location或Lookups\IP Geo-intelligence資料夾視窗。
1. 按一下右鍵資料檔案的[!DNL Temp]列，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]**>*，將檔案保存到資料工作台伺服器電腦。

   如果您正在運行群集，請將檔案上載到群集中的主資料工作台伺服器。

## 更新IPLookup轉換{#section-a8b99afe3eb04afabe88e15bd465f935}

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Dataset]**、**[!UICONTROL Transformation]**&#x200B;和&#x200B;**[!UICONTROL Geography]**。

1. 按一下右鍵[!DNL IP Lookup.cfg]旁邊的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 此檔案的複選標籤會出現在[!DNL User]列中。

1. 按一下右鍵新複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 將出現一個轉換配置窗口。

1. 在窗口中，按一下&#x200B;**[!UICONTROL Transformation]** ，然後按一下&#x200B;**[!UICONTROL Transformations]**。

1. 找到並按一下&#x200B;**[!UICONTROL IPLookup Quova]**&#x200B;或&#x200B;**[!UICONTROL IPLookup Digital Envoy]**。

1. 對於「檔案」參數，更新檔案的名稱，使其與Adobe提供的新資料([!DNL .bin])檔案的名稱匹配。
1. 通過按一下右鍵配置窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]**&#x200B;來保存轉換配置檔案。

1. 通過按一下右鍵[!DNL User]列中[!DNL IP Lookup.cfg]旁的複選標籤並按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]*** ，將修改的配置檔案保存到使用資料服務的每個配置檔案。 資料集描述檔的同步後，開始重新轉換資料。

   有關資料集的重新轉換的資訊，請參閱&#x200B;*資料集配置指南*&#x200B;中的「重新處理和重新轉換」一章。

   >[!NOTE]
   >
   >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案（包括[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]配置檔案），因為在安裝這些配置檔案的更新時將覆蓋您所做的更改。

如果您已安裝5.1版或更新版本的[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]資料服務，則您已完成資料服務更新。 但是，如果您在5.1版之前安裝了[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]資料服務，則必須完成以下附加過程。

## 取代查閱檔案{#section-ced1efa38a76419d812edd35423dbff7}

只有在5.1版之前安裝了[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]資料服務時，才應完成以下步驟。

1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]**&#x200B;或&#x200B;**[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**，然後按一下&#x200B;**[!UICONTROL Maps]**&#x200B;以檢視其內容。

1. 在&#x200B;**[!UICONTROL Maps]**&#x200B;的&#x200B;**[!UICONTROL Temp]**&#x200B;欄中按一下滑鼠右鍵，然後按一下&#x200B;**[!UICONTROL Open]** > ***[!UICONTROL folder]**>*。

1. 將Adobe提供的新[!DNL .txt]檔案複製到「映射」資料夾窗口。
1. 在[!DNL .txt]檔案的[!DNL Temp]欄中按一下滑鼠右鍵，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]***，將檔案儲存至資料工作台伺服器。

>[!NOTE]
>
>如果您正在運行群集，請將檔案上載到群集中的主資料工作台伺服器。

## 更新層檔案{#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>只有在5.1版之前安裝了[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]資料服務時，才應完成以下步驟。

針對參照[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]查閱([!DNL .txt])檔案的每個圖層([!DNL .layer])檔案，完成這些步驟。

1. 在資料工作台伺服器安裝目錄中的Profiles\*data service name*\Maps資料夾中，在文本編輯器（如記事本）中開啟[!DNL .layer]檔案。

1. 在[!DNL Data Paths]向量中，更新[!DNL .txt]查閱檔案的名稱，以符合Adobe提供的新[!DNL .txt]檔案名稱，如下列檔案範例中反白顯示：

   ```
   Layer = ElementPointLayer:
     Data Paths = vector: 1 items
       0 = Path: Maps\\LookupFileName.txt
     Longitude Column = string: LongitudeColumnName
     Latitude Column = string: LatitudeColumnName
     Name Column = string: LocationColumnName
     Key Column = string: KeyColumnName
     Dimension = ref: wdata/model/dim/DimensionName
     Metric = ref: wdata/model/metric/MetricName
   ```

1. 保存更新的圖層檔案。
1. 對參照[!DNL IP Geo-intelligence]或[!DNL IP Geo-location] [!DNL .txt]檔案的每個[!DNL .layer]檔案重複步驟2和3。
