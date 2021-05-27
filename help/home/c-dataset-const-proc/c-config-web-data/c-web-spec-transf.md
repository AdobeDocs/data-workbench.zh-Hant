---
description: 轉換資料集包含檔案中定義之Web特定設定的相關資訊，這些檔案隨網站的Adobe設定檔一併傳送。
title: 轉換的 Web 專屬設定
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
exl-id: 737f5e7a-7ab3-4ff7-8d92-7ccd87c28743
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 1%

---

# 轉換的 Web 專屬設定{#web-specific-settings-for-transformation}

轉換資料集包含檔案中定義之Web特定設定的相關資訊，這些檔案隨網站的Adobe設定檔一併傳送。

由這些設定定義的條件、維度和參數，會在資料集建構的轉換階段建立。

* [頁面檢視條件](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [URIDimension](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [反向連結Dimension](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [工作階段參數](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## 頁面檢視條件 {#section-cc2807a12a88492f8b64a43234a1f835}

[!DNL Page View Condition]是條件操作，可判斷是否應將特定記錄項目（即頁面要求）納入所收集有關訪客頁面檢視歷史記錄的資料中。 當記錄項目滿足[!DNL Page View Condition]時，它會成為「頁面檢視」可數維度的元素。 如果日誌條目不滿足[!DNL Page View Condition]，其資料欄位仍可由其他維訪問。 除了「頁面檢視」維度，下列維度也可能受到[!DNL Page View Condition]結果的影響：

* **[!DNL URI]和 [!DNL Page]:** 這些維度會直接受 [!DNL Page View Condition]影響。如果給定頁面未傳遞[!DNL Page View Condition,]，則它不會包含在URI或頁面維中。

* **[!DNL Visitor Page Views]和 [!DNL Session Page Views]:** 「訪客頁面檢視」和「工作階段頁面檢視」維度是訪客在指定工作階段中檢視或在指定工作階段中檢視的頁面數計數。由[!DNL Page View Condition]篩選掉的頁面不屬於此計數。

* **工作階段編號：** 對 [!DNL Page View Condition] 「工作階段編號」維度有間接影響。「會話編號」維在[!DNL Page View Condition]之前建立；因此，在考慮[!DNL Session Number]與[!DNL Page Views]相關時，可能有沒有頁面檢視的工作階段。

您的[!DNL Site]預設實作包含[!DNL Transformation Dataset Include]檔案，其中定義了「頁面檢視」可數維度和相關的[!DNL Page View Condition]。

有關可數維的資訊，請參閱[擴展Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**編輯頁面檢視條件的組態設定**

1. 在資料集設定檔中開啟[!DNL Profile Manager]，並開啟[!DNL Dataset\Transformation\Traffic\Page View.cfg]檔案。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]實作，則存在這些組態設定的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯[!DNL Page View Condition]參數的值。 請使用下列範例作為指南。 在此檔案中，[!DNL Page View Condition]由[!DNL Copy]轉換定義。 請注意，此檔案也包含「頁面檢視」可數維度的定義。

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >有關可數維的資訊，請參閱[擴展Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。 有關[!DNL Copy]轉換的資訊，請參閱[資料轉換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**，然後按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存檔案。

1. 若要讓本機所做的變更生效，請在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中檔案的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***，其中，設定檔名稱是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

## URIDimension{#section-348f7e9099d049d197a7cdcbc8a6c234}

如果您使用[!DNL Site]，則需要定義URI維，其元素為已檢視之網站頁面的URI源。 預設實施包括[!DNL Transformation Dataset Include]檔案，其中定義了URI簡單維。

有關簡單維的資訊，請參閱[擴展Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**要編輯URI維的配置設定**

1. 在資料集設定檔中開啟[!DNL Profile Manager]，並開啟[!DNL Dataset\Transformation\Traffic\URI.cfg]檔案。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]實作，則存在這些組態設定的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯檔案參數的值。 請使用下列範例和資訊作為指南。

![](assets/cfg_WebParameters_URI.png)

URI維的配置設定包括以下兩個參數：

* **區分大小寫：** True或False。若為true，則在識別不重複頁面時會考量字母大小寫（上/下）。 預設值為true。
* **最大元素：** URI維的最大元素數（即URI）。預設值為 32768。

   >[!NOTE]
   >
   >更改此值可能會導致嚴重的效能問題。 若沒有諮詢Adobe，請勿變更此值。

* 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**，然後按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存[!DNL URI.cfg]檔案。

* 若要讓本機所做的變更生效，請在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中檔案的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***，其中，設定檔名稱是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

## 反向連結Dimension{#section-8a97ec34d18b4814b5f95495ac4f8638}

若您使用[!DNL Site]，則需要定義「反向連結」維度，其元素包含所有工作階段中第一個記錄項目之反向連結的第二層網域。 您的預設實作包含[!DNL Transformation Dataset Include]檔案，其中定義了反向連結簡單維度。

有關簡單維的資訊，請參閱[擴展Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**編輯反向連結維度的組態設定**

1. 在資料集設定檔中開啟[!DNL Profile Manager]，並開啟[!DNL Dataset\Transformation\Traffic\Referrer.cfg]檔案。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]實作，則存在這些組態設定的檔案可能與描述的位置不同。

1. 視需要檢閱或編輯檔案參數的值。 請使用下列範例和資訊作為指南。

   ![](assets/cfg_WebParameters_Referrer.png)

   「反向連結」維度的組態設定包含「最大元素」參數，該參數會指定「反向連結」維度的元素數量上限（即反向連結）。 預設值為 32768。

   >[!NOTE]
   >
   >在上述範例中， [!DNL Maximum Elements]參數設為0。 此參數設為0時，Data Workbench伺服器會使用其內部預設值32768。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**，然後按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存[!DNL Referrer.cfg]檔案。

1. 若要讓本機所做的變更生效，請在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中檔案的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***，其中，設定檔名稱是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

## 會話參數{#section-0a209b0c504041a5801f7f71a963c8b1}

如果您使用[!DNL Site]，您可以指定參數來定義網站上訪客工作階段的界限。 這些參數僅在[!DNL Site]實作的[!DNL Transformation Dataset Include]檔案中定義時有效。

以下參數是唯一的，因為它們可以是[!DNL Transformation Dataset Include]檔案[!DNL Parameters]向量的成員，或者可以作為[!DNL Transformation.cfg]檔案中的單個參數列出。 參數可以只定義一次，因此這些參數可在[!DNL Transformation.cfg]檔案或資料集包含檔案的[!DNL Parameters]向量中定義，而不是在兩個檔案中定義。
**最大會話持續時間和會話超時**

「工作階段長度上限」和「工作階段逾時」是定義訪客工作階段長度的字串參數。 這些參數可與Internal Domains參數搭配使用，以判斷工作階段長度。

Maximum Session Duration指定啟動新會話之前的最長會話長度。 這可讓具有自動內容重新整理的網頁不會建立任意長度的工作階段。 如果點按的反向連結設為「內部網域」參數中的其中一個項目，則此逾時可用來定義工作階段的結尾。 不論包含多少點按，任何工作階段都不得超過指定的最大工作階段持續時間。 建議值為48小時。

「工作階段逾時」會指定在指定訪客的記錄項目之間需經過的時間長度，以判斷一個工作階段的結尾與新工作階段的開始（即用來定義使用者工作階段的一般逾時）。 此參數的建議值為30分鐘。 如果點按的反向連結未設為「內部網域」參數中的其中一個反向連結，系統會使用此逾時來定義工作階段。 如果記錄項目的cs(referrer-domain)位於內部網域清單中，則「最大工作階段期間」會判斷目前記錄項目是現有工作階段的一部分，還是新工作階段的開始。

請考量在瀏覽網站期間，訪客被叫離電腦的時間比工作階段逾時長的情況。 回來後，他繼續瀏覽離開的地方。 由於訪客從未離開網站或關閉瀏覽器，因此其下次點按的cs（反向連結網域）與內部網域相同，而只要未達到「最大工作階段期間」設定，其原始工作階段仍會保持作用中。 如果網站的網域列為內部網域，且未達到逾時上限，則訪客的互動會顯示為單一工作階段，而非兩個個別的工作階段。 不過，如果訪客返回電腦，而下次點按有外部（或空白）反向連結，則會開始新的工作階段。

>[!NOTE]
>
>[!DNL Sessionize]轉換的[!DNL Timeout Condition]在決定訪客工作階段的長度時也起到作用。 如果「會話超時」和「最大會話持續時間」不適用，則檢查[!DNL Timeout Condition]以確定是否應將日誌條目視為新會話的開始。 如需詳細資訊，請參閱[資料轉換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

**編輯「最大會話持續時間」和「會話超時」參數**

若您使用[!DNL Site]，您的預設實作可能包含[!DNL Transformation Dataset Include]檔案，其中會指定這些參數的名稱和建議值。

1. 開啟資料集設定檔中的[!DNL Profile Manager]，然後前往[!DNL Dataset\Transformation\Traffic\Session Parameters.cfg]。

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]的實作，則定義這些參數的檔案可能與說明的位置不同。

1. 視需要編輯參數的值。 請務必指定所需的單位（分鐘、小時等）。

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存[!DNL Session Parameters.cfg]檔案。

1. 若要讓本機所做的變更生效，請在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中檔案的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL profile name]**，其中，設定檔名稱是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

**[!DNL Internal Domains]**

[!DNL Internal Domains] 是向量參數，列出應視為特定網站一部分的網域層級主機（內部反向連結）。這些主機會從反向連結維度（外部反向連結資訊的清單）中移除。 當cs(referrer-domain)符合內部網域集中所列的任何字串時，會忽略「工作階段逾時」 ，並使用「最大工作階段持續時間」來判斷工作階段長度。

當訪客以超過工作階段逾時的方式在公司的多個關聯網域之間移動時，內部網域參數也可用來防止新工作階段的開始。 例如，假設某家公司的網站部分分割為兩個網域：一個已記錄([!DNL xyz.com])，另一個未記錄([!DNL xyz-unlogged.com])。 如果這些網站的整合方式有助於流量在兩個網域間的順暢移動，則當訪客每次從[!DNL xyz-unlogged.com]網域移回[!DNL xyz.com]網域時，不需要產生不同的工作階段。 將[!DNL xyz-unlogged.com]列為內部網域可防止由於這兩個網域的流量而將工作階段分割為多個工作階段，只要未達到「最大工作階段持續時間」設定。

**新增內部網域的方式**

如果您使用[!DNL Site]，預設實作會包含[!DNL Transformation Dataset Include]檔案，以定義內部網域參數。 在此檔案中，參數名為；您只需輸入要包含的內部網域，然後儲存更新的檔案即可。

1. 開啟資料集設定檔中的[!DNL Profile Manager]，然後前往[!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >如果您已自訂[!DNL Site]的實作，則定義內部網域參數的檔案可能與說明的位置不同。

1. 按一下右鍵&#x200B;**[!UICONTROL Value]**&#x200B;獲取「內部域」向量參數，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Value]**。

1. 視需要編輯值。

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存[!DNL Internal Domains.cfg]檔案。

1. 若要讓本機所做的變更生效，請在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中檔案的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***，其中，設定檔名稱是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。
