---
description: 如果您訂閱任一資料服務，則必須定期更新Adobe提供的資料服務檔案。
title: 更新資料服務檔案
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# 更新資料服務檔案{#updating-data-service-files}

如果您訂閱任一資料服務，則必須定期更新Adobe提供的資料服務檔案。

若要這麼做，您必須擁有Data Workbench伺服器上檔案的存取權。

要載入[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]資料檔案，必須完成以下過程。

## 替換資料檔案{#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. 在Data Workbench中，在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟[!DNL Servers Manager]工作區。

1. 在[!DNL Servers Manager]視窗中，以滑鼠右鍵按一下您要載入檔案的Data Workbench伺服器圖示，然後按一下&#x200B;**[!UICONTROL Server Files]**。

1. 在[!DNL Server Files Manager]中，按一下右鍵&#x200B;**[!UICONTROL Lookups\IP Geo-location]**&#x200B;或&#x200B;**[!UICONTROL Lookups\IP Geo-intelligence]**&#x200B;的&#x200B;**[!UICONTROL Temp]**&#x200B;列，然後按一下&#x200B;**[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*。

1. 將Adobe提供的[!DNL .bin]資料檔案複製到Lookups\IP Geo-location或Lookups\IP Geo-intelligence資料夾窗口。
1. 以滑鼠右鍵按一下資料檔案的[!DNL Temp]欄，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*，將檔案儲存至Data Workbench伺服器電腦。

   如果您執行叢集，請將檔案上傳至叢集中的主資料工作台伺服器。

## 更新IPLookup轉換{#section-a8b99afe3eb04afabe88e15bd465f935}

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Dataset]**、**[!UICONTROL Transformation]**&#x200B;和&#x200B;**[!UICONTROL Geography]**。

1. 按一下右鍵[!DNL IP Lookup.cfg]旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。

1. 按一下右鍵新複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 將顯示轉換配置窗口。

1. 在視窗中，按一下&#x200B;**[!UICONTROL Transformation]**，然後按一下&#x200B;**[!UICONTROL Transformations]**。

1. 找到並按一下&#x200B;**[!UICONTROL IPLookup Quova]**&#x200B;或&#x200B;**[!UICONTROL IPLookup Digital Envoy]**。

1. 對於File參數，更新檔案的名稱以與Adobe提供的新資料([!DNL .bin])檔案的名稱匹配。
1. 按一下右鍵配置窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存轉換配置檔案。

1. 按一下右鍵[!DNL User]列中[!DNL IP Lookup.cfg]旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***，將修改的配置檔案保存到使用資料服務的每個配置檔案。 同步資料集設定檔後，即會開始重新轉換資料。

   如需資料集重新轉換的相關資訊，請參閱&#x200B;*資料集組態指南*&#x200B;的重新處理和重新轉換章節。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔（包括[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]設定檔），因為您在安裝這些設定檔的更新時，變更會遭到覆寫。

如果安裝了5.1版或更新版本的[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]資料服務，則已完成資料服務更新。 但是，如果安裝了5.1版之前的[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]資料服務，則必須完成以下附加過程。

## 替換查找檔案{#section-ced1efa38a76419d812edd35423dbff7}

只有在5.1版之前安裝了[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]資料服務時，才應完成下列步驟。

1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]**&#x200B;或&#x200B;**[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**，然後按一下&#x200B;**[!UICONTROL Maps]**&#x200B;以檢視其內容。

1. 在&#x200B;**[!UICONTROL Maps]**&#x200B;的&#x200B;**[!UICONTROL Temp]**&#x200B;欄中按一下右鍵，然後按一下&#x200B;**[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*。

1. 將Adobe提供的新[!DNL .txt]檔案複製到「映射」資料夾窗口。
1. 以滑鼠右鍵按一下[!DNL .txt]檔案[!DNL Temp]欄中的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*，將檔案儲存至Data Workbench伺服器電腦。

>[!NOTE]
>
>如果您執行叢集，請將檔案上傳至叢集中的主資料工作台伺服器。

## 更新層檔案{#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>只有在5.1版之前安裝了[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]資料服務時，才應完成下列步驟。

針對參考[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]查閱([!DNL .txt])檔案的每個層([!DNL .layer])檔案完成這些步驟。

1. 在Data Workbench伺服器安裝目錄內的Profiles\*data service name*\Maps資料夾中，在文字編輯器（如記事本）中開啟[!DNL .layer]檔案。

1. 在[!DNL Data Paths]向量中，更新[!DNL .txt]查閱檔案的名稱，以符合Adobe提供的新[!DNL .txt]檔案的名稱，如下列檔案範例中強調顯示：

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

1. 保存更新的層檔案。
1. 對引用[!DNL IP Geo-intelligence]或[!DNL IP Geo-location] [!DNL .txt]檔案的每個[!DNL .layer]檔案重複步驟2和3。
