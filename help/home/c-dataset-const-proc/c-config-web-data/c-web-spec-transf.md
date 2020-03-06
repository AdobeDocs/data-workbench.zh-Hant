---
description: 在轉換資料集中定義的網頁特定設定相關資訊，包括隨Adobe網站設定檔傳送的檔案。
solution: Analytics
title: 用於轉換的Web特定設定
topic: Data workbench
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 用於轉換的Web特定設定{#web-specific-settings-for-transformation}

在轉換資料集中定義的網頁特定設定相關資訊，包括隨Adobe網站設定檔傳送的檔案。

這些設定所定義的條件、尺寸和參數是在資料集建構的轉換階段建立。

* [頁面檢視條件](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [URI維](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [反向連結維度](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [會話參數](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## 頁面檢視條件 {#section-cc2807a12a88492f8b64a43234a1f835}

此條 [!DNL Page View Condition] 件操作可判斷特定記錄項目（即頁面請求）是否應包含在收集的訪客頁面檢視歷史記錄相關資料中。 當日誌條目滿足該條 [!DNL Page View Condition]目時，它將成為「頁面視圖」可計數維的元素。 如果日誌條目不滿足，則其 [!DNL Page View Condition]他維度仍可以訪問其資料欄位。 除了「頁面檢視」維度外，下列維度也可能受到下列結果的影響 [!DNL Page View Condition]:

* **[!DNL URI]和[!DNL Page]:**這些維度會直接受到[!DNL Page View Condition]。 如果指定頁面未傳遞，[!DNL Page View Condition,]則不會包含在URI或頁面維度中。

* **[!DNL Visitor Page Views]和[!DNL Session Page Views]:**「訪客頁面檢視」和「工作階段頁面檢視」維度是訪客在指定工作階段中檢視的頁面數目計數。 由篩選掉的頁[!DNL Page View Condition]面不屬於此計數。

* **會話編號：** 對「 [!DNL Page View Condition] 會話編號」維有間接影響。 「會話編號」維建立於 [!DNL Page View Condition];因此，在考慮 [!DNL Session Number] 與相關的作業時 [!DNL Page Views]，可能沒有頁面檢視的作業。

您的預設實 [!DNL Site] 作包 [!DNL Transformation Dataset Include] 含一個檔案，其中定義了「頁面檢視」可計數維度和 [!DNL Page View Condition] 相關維度。

如需可計數維度的詳細資訊，請參 [閱延伸維度](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**若要編輯頁面檢視條件的組態設定**

1. 在資料集 [!DNL Profile Manager] 設定檔中開啟，並開啟 [!DNL Dataset\Transformation\Traffic\Page View.cfg] 檔案。

   >[!NOTE]
   >
   >如果您已自訂實作， [!DNL Site]則這些組態設定所在的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯參數 [!DNL Page View Condition] 的值。 以下範例為指南。 在此檔案中， [!DNL Page View Condition] 由轉換定 [!DNL Copy] 義。 請注意，此檔案也包含「頁面檢視」可計數維度的定義。

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >如需可計數維度的詳細資訊，請參 [閱延伸維度](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。 有關轉換的信 [!DNL Copy] 息，請參閱 [資料轉換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

1. 以滑鼠右鍵按一下視窗頂 **[!UICONTROL (modified)]** 端的檔案，然後按一下以儲存檔案 **[!UICONTROL Save]**。

1. 若要讓本機所做的變更生效，請在欄中 [!DNL Profile Manager]，以滑鼠右鍵按一下該檔案的核取標籤，然後按一下 [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***，其中描述檔名稱是資料集描述檔的名稱或資料集包含檔案所屬的繼承描述檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

## URI維 {#section-348f7e9099d049d197a7cdcbc8a6c234}

如果您正在使用 [!DNL Site]，則需要定義URI維度，其元素是所檢視之網站頁面的URI系列。 您的預設實施包 [!DNL Transformation Dataset Include] 括定義URI簡單維的檔案。

如需簡單維度的詳細資訊，請參 [閱延伸維度](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**要編輯URI維的配置設定**

1. 在資料集 [!DNL Profile Manager] 設定檔中開啟，並開啟 [!DNL Dataset\Transformation\Traffic\URI.cfg] 檔案。

   >[!NOTE]
   >
   >如果您已自訂實作， [!DNL Site]則這些組態設定所在的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯檔案參數的值。 使用下列範例和資訊做為參考線。

![](assets/cfg_WebParameters_URI.png)

URI維的配置設定包括以下兩個參數：

* **區分大小寫：** 是非。 如果為true，則在識別獨特頁面時會考慮字母大小寫（上／下）。 預設值為true。
* **最大元素：** URI維的最大元素數（即URI）。 預設值為 32768。

   >[!NOTE]
   >
   >更改此值可能會導致嚴重的效能問題。 不要在未諮詢Adobe的情況下變更此值。

* 以滑鼠 [!DNL URI.cfg] 右鍵按一下視窗頂 **[!UICONTROL (modified)]** 端的檔案，然後按一下以儲存檔案 **[!UICONTROL Save]**。

* 若要讓本機所做的變更生效，請在欄中 [!DNL Profile Manager]，以滑鼠右鍵按一下該檔案的核取標籤，然後按一下 [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***，其中描述檔名稱是資料集描述檔的名稱或資料集包含檔案所屬的繼承描述檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

## 反向連結維度 {#section-8a97ec34d18b4814b5f95495ac4f8638}

如果您正在使用 [!DNL Site]，則需要定義「反向連結」維度，其元素由所有作業中第一個記錄項目的反向連結第二層級網域組成。 您的預設實作包含 [!DNL Transformation Dataset Include] 已定義「反向連結」簡單維度的檔案。

如需簡單維度的詳細資訊，請參 [閱延伸維度](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**若要編輯「反向連結」維度的組態設定**

1. 在資料集 [!DNL Profile Manager] 設定檔中開啟，並開啟 [!DNL Dataset\Transformation\Traffic\Referrer.cfg] 檔案。

   >[!NOTE]
   >
   >如果您已自訂實作， [!DNL Site]則這些組態設定所在的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯檔案參數的值。 使用下列範例和資訊做為參考線。

   ![](assets/cfg_WebParameters_Referrer.png)

   「反向連結」維度的組態設定包括「最大元素」參數，此參數會指定「反向連結」維度的元素數目上限（即反向連結）。 預設值為 32768。

   >[!NOTE]
   >
   >在上述範例中，參 [!DNL Maximum Elements] 數設定為0。 當此參數設為0時，資料工作台伺服器會使用其內部預設值32768。

1. 以滑鼠 [!DNL Referrer.cfg] 右鍵按一下視窗頂 **[!UICONTROL (modified)]** 端的檔案，然後按一下以儲存檔案 **[!UICONTROL Save]**。

1. 若要讓本機所做的變更生效，請在欄中 [!DNL Profile Manager]，以滑鼠右鍵按一下該檔案的核取標籤，然後按一下 [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***，其中描述檔名稱是資料集描述檔的名稱或資料集包含檔案所屬的繼承描述檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

## 會話參數 {#section-0a209b0c504041a5801f7f71a963c8b1}

如果您正在使用 [!DNL Site]，可以指定參數來定義網站上訪客作業的界限。 這些參數只有在實作中的檔案中定 [!DNL Transformation Dataset Include] 義時才有 [!DNL Site] 效。

以下參數是唯一的，因為它們可以是 [!DNL Transformation Dataset Include] 檔案向量的 [!DNL Parameters] 成員，或者可以作為檔案中的單個參數 [!DNL Transformation.cfg]列出。 參數可精確定義一次，因此這些參數可在檔 [!DNL Transformation.cfg]案中或在資料集 [!DNL Parameters] 包含檔案的向量中定義——不在兩個檔案中。
**最大會話持續時間和會話超時**

「最大作業持續時間」和「作業逾時」是字串參數，可定義訪客作業的長度。 這些參數可搭配「內部網域」參數運作，以判斷工作階段長度。

「最大會話持續時間」指定啟動新會話前的會話最長長度。 如此可讓具有自動內容重新整理功能的網頁，而不需建立任意長度的工作階段。 如果點按的反向連結設定為「內部網域」參數中的其中一個項目，則此逾時會用來定義工作階段的結束。 不論會話包含多少次點按，都不得超過指定的「最大會話持續時間」。 建議值為48小時。

「作業逾時」會指定在指定訪客的記錄項目之間需要傳遞的時間量，以決定一個作業結束和新作業開始（即用來定義使用者作業的典型逾時）。 此參數的建議值為30分鐘。 如果點按的反向連結未設定為「內部網域」參數中的其中一個反向連結，則會使用此逾時來定義工作階段。 如果記錄項的cs(referrer-domain)位於內部網域清單中，則「最大作業持續時間」會決定目前的記錄項是現有作業的一部分，還是新作業的開始。

請考慮以下情況：訪客在瀏覽網站時被呼叫離開其電腦的時間比「作業逾時」長一段時間。 回來後，他繼續瀏覽他離開的地方。 由於訪客從不離開網站或關閉瀏覽器，因此下次點按的cs（反向連結網域）與內部網域相同，而且只要未達到「最大作業持續時間」設定，其原始作業仍會保持作用中。 如果網站的網域列為內部網域，且未達到最大逾時值，則訪客的互動會顯示為單一作業，而非兩個個別作業。 不過，如果訪客返回其電腦，而下次點按時有外部（或空白）反向連結，則會開始新的工作階段。

>[!NOTE]
>
>轉 [!DNL Sessionize] 換在 [!DNL Timeout Condition] 決定訪客作業長度方面也起到作用。 如果「會話超時」和「最大會話持續時間」不適用，則 [!DNL Timeout Condition] 將選中該選項以確定是否應將日誌條目視為新會話的開始。 For more information, see [Data Transformations](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**要編輯「最大會話持續時間」和「會話超時」參數，請執行以下操作：**

如果您正在使用 [!DNL Site]，預設實作可能會包含 [!DNL Transformation Dataset Include] 一個檔案，其中會指定這些參數的名稱和建議值。

1. 在資料集 [!DNL Profile Manager] 設定檔中開啟，然後前往 [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg]。

   >[!NOTE]
   >
   >如果您已自訂實作， [!DNL Site]則定義這些參數的檔案可能與描述的位置不同。

1. 視需要編輯參數的值。 請務必指定所需的單位（分鐘、小時等）。

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. 以滑鼠 [!DNL Session Parameters.cfg] 右鍵按一下視窗上 **[!UICONTROL (modified)]** 方的滑鼠右鍵並按一下，以儲存檔案 **[!UICONTROL Save]**。

1. 若要讓本機所做的變更生效，請在欄中以滑鼠右鍵按一下檔案的核取標籤，然後按一下 [!DNL Profile Manager]> [!DNL User]**[!UICONTROL Save to]****[!UICONTROL profile name]**，其中描述檔名稱是資料集描述檔的名稱，或是資料集包含檔案所屬的繼承描述檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

**[!DNL Internal Domains]**

[!DNL Internal Domains] 是向量參數，列出網域層級主機（內部反向連結），應視為特定網站的一部分。 這些主機會從反向連結維度（外部反向連結資訊的清單）中移除。 當cs(referrer-domain)符合內部網域集中所列的任何字串時，會忽略「作業逾時」，並使用「最大作業持續時間」來判斷作業長度。

「內部網域」參數也可用來防止訪客在超過工作階段逾時的公司多個關聯網域間移動時，啟動新工作階段。 例如，假設某家公司的網站部分被分割為兩個網域：一個是記錄( [!DNL xyz.com])，另一個是未記錄( [!DNL xyz-unlogged.com])。 如果這些網站的整合方式有助於流量在兩個網域之間順暢地移動，則訪客每次從網域移回網域時，不需要產生 [!DNL xyz-unlogged.com] 不同的作 [!DNL xyz.com] 業。 列 [!DNL xyz-unlogged.com] 出為內部網域，可避免由於這兩個網域的流量而將工作階段分割為多個工作階段，只要未達到「最大工作階段持續時間」設定即可。

**若要新增內部網域**

如果您正在使用， [!DNL Site]預設實作會包含用 [!DNL Transformation Dataset Include] 於定義內部網域參數的檔案。 在此檔案中，參數名為；您只需輸入要包含的內部網域，並儲存更新的檔案。

1. 在資料集 [!DNL Profile Manager] 設定檔中開啟，然後前往 [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >如果您已自訂實作， [!DNL Site]則定義「內部網域」參數的檔案可能與描述的位置不同。

1. 以滑鼠右鍵按 **[!UICONTROL Value]** 一下「內部網域」向量參數，然後按一 **[!UICONTROL Add new]** 下> **[!UICONTROL Value]**。

1. 視需要編輯值。

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. 以滑鼠 [!DNL Internal Domains.cfg] 右鍵按一下視窗上 **[!UICONTROL (modified)]** 方的滑鼠右鍵並按一下，以儲存檔案 **[!UICONTROL Save]**。

1. 若要讓本機所做的變更生效，請在欄中 [!DNL Profile Manager]，以滑鼠右鍵按一下該檔案的核取標籤，然後按一下 [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***，其中描述檔名稱是資料集描述檔的名稱或資料集包含檔案所屬的繼承描述檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

