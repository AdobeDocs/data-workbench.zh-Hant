---
description: Transformation Dataset中定義的Web特定設定資訊包括與站點Adobe配置檔案一起提供的檔案。
title: 轉換的 Web 專屬設定
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
exl-id: 737f5e7a-7ab3-4ff7-8d92-7ccd87c28743
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 1%

---

# 轉換的 Web 專屬設定{#web-specific-settings-for-transformation}

Transformation Dataset中定義的Web特定設定資訊包括與站點Adobe配置檔案一起提供的檔案。

這些設定所定義的條件、尺寸和參數是在資料集建構的轉換階段建立。

* [頁面檢視條件](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [URIDimension](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [反向連結Dimension](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [會話參數](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## 頁面檢視條件 {#section-cc2807a12a88492f8b64a43234a1f835}

[!DNL Page View Condition]是一項條件操作，可決定是否應將特定記錄項目（即頁面請求）納入蒐集到的訪客頁面檢視歷史記錄相關資料中。 當日誌條目滿足[!DNL Page View Condition]時，它將成為「頁面視圖」可計數維的元素。 如果日誌條目不滿足[!DNL Page View Condition] ，則其資料欄位仍可由其他維訪問。 除了「頁面檢視」維度外，下列維度也會受[!DNL Page View Condition]結果的影響：

* **[!DNL URI]和 [!DNL Page]：這** 些維度直接受到 [!DNL Page View Condition]。如果指定頁面未傳遞[!DNL Page View Condition,]，則它不會包含在URI或頁面維度中。

* **[!DNL Visitor Page Views]和 [!DNL Session Page Views]: 「訪** 客頁面檢視」和「作業頁面檢視」維度是訪客在指定作業中檢視的頁面數目計數。由[!DNL Page View Condition]篩選掉的頁面不屬於此計數。

* **會話編** 號： [!DNL Page View Condition] 對「會話編號」維有間接影響。在[!DNL Page View Condition]之前建立「會話編號」維；因此，在考慮與[!DNL Page Views]相關的[!DNL Session Number]時，可能沒有頁面檢視的作業。

您預設的[!DNL Site]實作包含[!DNL Transformation Dataset Include]檔案，其中定義了「頁面檢視」可計數維度和相關的[!DNL Page View Condition]。

有關可計數維的資訊，請參見[擴展Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**若要編輯頁面檢視條件的組態設定**

1. 在資料集描述檔中開啟[!DNL Profile Manager]，並開啟[!DNL Dataset\Transformation\Traffic\Page View.cfg]檔案。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]的實作，則這些組態設定所在的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯[!DNL Page View Condition]參數的值。 以下範例為指南。 在此檔案中，[!DNL Page View Condition]由[!DNL Copy]轉換定義。 請注意，此檔案也包含「頁面檢視」可計數維度的定義。

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >有關可計數維的資訊，請參見[擴展Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。 有關[!DNL Copy]轉換的資訊，請參見[資料轉換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**&#x200B;保存檔案。

1. 要使本地更改生效，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>* ，其中配置檔案名稱是資料集配置檔案的名稱或資料集包含檔案所屬的繼承配置檔案。

   >[!NOTE]
   >
   >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。

## URIDimension{#section-348f7e9099d049d197a7cdcbc8a6c234}

如果您使用[!DNL Site]，則需要定義URI維，其元素是所檢視網站頁面的URI源。 預設實施包括定義URI簡單維的[!DNL Transformation Dataset Include]檔案。

有關簡單維的資訊，請參見[擴展Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**要編輯URI維的配置設定**

1. 在資料集描述檔中開啟[!DNL Profile Manager]，並開啟[!DNL Dataset\Transformation\Traffic\URI.cfg]檔案。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]的實作，則這些組態設定所在的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯檔案參數的值。 使用下列範例和資訊做為參考線。

![](assets/cfg_WebParameters_URI.png)

URI維的配置設定包括以下兩個參數：

* **區分大小寫：** 是真或假。如果為true，則在識別獨特頁面時會考慮字母大小寫（上／下）。 預設值為true。
* **最大元** 素：URI維的最大元素數（即URI）。預設值為 32768。

   >[!NOTE]
   >
   >更改此值可能會導致嚴重的效能問題。 不要在未諮詢Adobe的情況下更改此值。

* 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]** ，保存[!DNL URI.cfg]檔案。

* 要使本地更改生效，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>* ，其中配置檔案名稱是資料集配置檔案的名稱或資料集包含檔案所屬的繼承配置檔案。

   >[!NOTE]
   >
   >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。

## 反向連結Dimension{#section-8a97ec34d18b4814b5f95495ac4f8638}

如果您使用[!DNL Site]，則需要定義「反向連結」維度，其元素包含所有作業中第一個記錄項目之反向連結的第二層級網域。 您的預設實作包含[!DNL Transformation Dataset Include]檔案，其中定義了「反向連結」簡單維度。

有關簡單維的資訊，請參見[擴展Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**若要編輯「反向連結」維度的組態設定**

1. 在資料集描述檔中開啟[!DNL Profile Manager]，並開啟[!DNL Dataset\Transformation\Traffic\Referrer.cfg]檔案。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]的實作，則這些組態設定所在的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯檔案參數的值。 使用下列範例和資訊做為參考線。

   ![](assets/cfg_WebParameters_Referrer.png)

   「反向連結」維度的組態設定包括「最大元素」參數，此參數會指定「反向連結」維度的元素數目上限（即反向連結）。 預設值為 32768。

   >[!NOTE]
   >
   >在上述範例中，[!DNL Maximum Elements]參數設為0。 當此參數設為0時，資料工作台伺服器會使用其內部預設值32768。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]** ，保存[!DNL Referrer.cfg]檔案。

1. 要使本地更改生效，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>* ，其中配置檔案名稱是資料集配置檔案的名稱或資料集包含檔案所屬的繼承配置檔案。

   >[!NOTE]
   >
   >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。

## 會話參數{#section-0a209b0c504041a5801f7f71a963c8b1}

如果您使用[!DNL Site]，可以指定定義網站訪客作業界限的參數。 這些參數僅在[!DNL Site]實作的[!DNL Transformation Dataset Include]檔案中定義時才有效。

以下參數是唯一的，因為它們可以是[!DNL Transformation Dataset Include]檔案[!DNL Parameters]向量的成員，或者它們可以作為[!DNL Transformation.cfg]檔案中的單個參數列出。 參數可精確定義一次，因此這些參數可在[!DNL Transformation.cfg]檔案中或資料集包含檔案的[!DNL Parameters]向量中定義——不在兩個檔案中。
**最大會話持續時間和會話超時**

「最大作業持續時間」和「作業逾時」是字串參數，可定義訪客作業的長度。 這些參數可搭配「內部網域」參數運作，以判斷工作階段長度。

「最大會話持續時間」指定啟動新會話前的會話最長長度。 如此可讓具有自動內容重新整理功能的網頁，而不需建立任意長度的工作階段。 如果點按的反向連結設定為「內部網域」參數中的其中一個項目，則此逾時會用來定義工作階段的結束。 不論會話包含多少次點按，都不得超過指定的「最大會話持續時間」。 建議值為48小時。

「作業逾時」會指定在指定訪客的記錄項目之間需要傳遞的時間量，以決定一個作業結束和新作業開始（即用來定義使用者作業的典型逾時）。 此參數的建議值為30分鐘。 如果點按的反向連結未設定為「內部網域」參數中的其中一個反向連結，則會使用此逾時來定義工作階段。 如果記錄項的cs(referrer-domain)位於內部網域清單中，則「最大作業持續時間」會決定目前的記錄項是現有作業的一部分，還是新作業的開始。

請考量在瀏覽網站時，訪客離開其電腦的時間比「工作階段逾時」長一段時間的情形。 回來後，他繼續瀏覽他離開的地方。 由於訪客從不離開網站或關閉瀏覽器，因此下次點按的cs（反向連結網域）與內部網域相同，而且只要未達到「最大作業持續時間」設定，其原始作業仍會保持作用中。 如果網站的網域列為內部網域，且未達到最大逾時值，則訪客的互動會顯示為單一作業，而非兩個個別作業。 不過，如果訪客返回其電腦，而下次點按時有外部（或空白）反向連結，則會開始新的工作階段。

>[!NOTE]
>
>[!DNL Sessionize]轉換的[!DNL Timeout Condition]在決定訪客作業長度時也起到作用。 如果「會話超時」和「最大會話持續時間」不適用，則選中[!DNL Timeout Condition]以確定是否應將日誌條目視為新會話的開始。 如需詳細資訊，請參閱[資料轉換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

**要編輯「最大會話持續時間」和「會話超時」參數，請執行以下操作：**

如果您使用[!DNL Site]，預設實作可能包含[!DNL Transformation Dataset Include]檔案，其中會指定這些參數的名稱和建議值。

1. 在資料集描述檔中開啟[!DNL Profile Manager]，然後前往[!DNL Dataset\Transformation\Traffic\Session Parameters.cfg]。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]的實作，則定義這些參數的檔案可能與描述的位置不同。

1. 視需要編輯參數的值。 請務必指定所需的單位（分鐘、小時等）。

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]** ，保存[!DNL Session Parameters.cfg]檔案。

1. 要使本地更改生效，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL profile name]** ，其中配置檔案名稱是資料集配置檔案的名稱或資料集包含檔案所屬的繼承配置檔案的名稱。

   >[!NOTE]
   >
   >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。

**[!DNL Internal Domains]**

[!DNL Internal Domains] 是向量參數，列出網域層級主機（內部反向連結），應視為特定網站的一部分。這些主機會從反向連結維度（外部反向連結資訊的清單）中移除。 當cs(referrer-domain)符合內部網域集中所列的任何字串時，會忽略「作業逾時」，並使用「最大作業持續時間」來判斷作業長度。

「內部網域」參數也可用來防止訪客在超過工作階段逾時的公司多個關聯網域間移動時，啟動新工作階段。 例如，假設某家公司的網站部分被分割為兩個網域：一個已記錄([!DNL xyz.com])，另一個未記錄([!DNL xyz-unlogged.com])。 如果這些網站的整合方式有助於流量在兩個網域之間順暢地移動，則訪客每次從[!DNL xyz-unlogged.com]網域移回[!DNL xyz.com]網域時，不需要產生不同的作業。 將[!DNL xyz-unlogged.com]列為內部網域，只要未達到「最大會話持續時間」設定，會防止會話被分割為多個會話，因為這兩個網域的通信量。

**若要新增內部網域**

如果您使用[!DNL Site]，則預設實作會包含一個[!DNL Transformation Dataset Include]檔案，以定義「內部網域」參數。 在此檔案中，參數名為；您只需輸入要包含的內部網域，並儲存更新的檔案。

1. 在資料集描述檔中開啟[!DNL Profile Manager]，然後前往[!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]的實施，則定義內部網域參數的檔案可能與描述的位置不同。

1. 按一下右鍵「內部域」向量參數&#x200B;**[!UICONTROL Value]** ，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Value]**。

1. 視需要編輯值。

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]** ，保存[!DNL Internal Domains.cfg]檔案。

1. 要使本地更改生效，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>* ，其中配置檔案名稱是資料集配置檔案的名稱或資料集包含檔案所屬的繼承配置檔案。

   >[!NOTE]
   >
   >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。
