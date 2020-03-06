---
description: 頁面覆蓋僅在網站應用程式中設定，但可針對其他應用程式設定。
solution: Analytics
title: 設定頁面覆蓋
topic: Data workbench
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定頁面覆蓋{#configure-a-page-overlay}

頁面覆蓋僅在網站應用程式中設定，但可針對其他應用程式設定。

如需為其他應用程式設定頁面覆蓋的詳細資訊，請聯絡Adobe諮詢服務。

頁面覆蓋圖視覺化是HTML連結分析的工具。 當您請求特定頁面的覆蓋時，資料工作台會以實際頁面在網頁瀏覽器中顯示的方式來擷取其快照，並根據您定義的規則運算式清單來剖析代表連結的HTML程式碼。 對於選定頁面上的每個連結，軟體會嘗試通過下列操作查找規則運算式模式匹配，直到找到第一個匹配。 如果有相符項目，連結會在頁面覆蓋圖中反白顯示。

頁面覆蓋只會在您新增色彩圖例至包含頁面覆蓋的工作區時顯示資料。

>[!NOTE]
>
>設定頁面覆蓋需要謹慎的設定工作，而且如果連結不正確地對應至資料，就可能產生誤導性結果。 為特定網站設定頁面覆蓋所涉及的工作，取決於網站頁面上HTML程式碼中的連結呈現方式。

頁面覆蓋(Page overlay)的性質，向使用者建議它顯示的「人們點按的位置」心理模型。如果支援視覺化的資料不符合此模型，可能會造成混淆。

在中 [!DNL Site]，連結通常代表「下一個URI」或「下一個連結」維度的元素，但您可以將連結對應至任何對分析有意義的維度。 如需為其他維度設定頁面覆蓋的詳細資訊，請聯絡Adobe諮詢服務。

>[!NOTE]
>
>不建議使用頁面覆蓋的頁面維度。 使用者可以重新命名頁面維度的元素，進而變更頁面覆蓋功能所依賴的連結語法。

若要設定頁面覆蓋 [!DNL Site]，您必須編輯兩個檔案：

* **[!DNL Page Overlay.vw]:**此檔案是建立頁面覆蓋視覺化的範本檔案。 您要設定頁面覆蓋的設定檔中必須至少有一個範本檔案。
* **[!DNL Page Overlay Link Templates.cfg]:**當頁面覆蓋視覺化載入頁面時，會自動識別頁面中的連結及其目的地。 若要將這些連結與資料中的元素建立關聯，您必須在此檔案中定義一組規則運算式。

   您可以定義多個規則運算式，以比對維度的元素。 定義運算式的順序很重要。 當您請求特定頁面的覆蓋時，資料工作台會以實際頁面在網頁瀏覽器中顯示的方式來擷取其快照，並根據您定義的規則運算式清單來剖析代表連結的HTML程式碼。 對於選定頁面上的每個連結，軟體會嘗試通過下列操作查找規則運算式模式匹配，直到找到第一個匹配。 使用與維度元素相符的第一個運算式。 因此，最好先列出具有最具體匹配模式的規則運算式，然後列出較少的具體表達式。 如果有相符項目，連結會在頁面覆蓋圖視覺化中反白顯示。

**若要設定網站的頁面覆蓋**

1. I

   在中， [!DNL Profile Manager]導覽至 **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**。

   >[!NOTE]
   >
   >「維元素」目錄包含在按一下右鍵維元素時出現的上下文菜單項。 例如，開啟URI表，然後選擇URI元素。 以滑鼠右鍵按一下URI並顯示「頁面覆蓋」。

1. 在URI資料夾中，按一下右鍵檔案旁的複選標 [!DNL Page Overlay.vw] 記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。
1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Notepad]**。
1. 指定「網域」(和「瀏覽器高度」（若有需要）)。

   ```
   window = simpleBorderWindow: 
     client = scrollWindow: 
       client = PageOverlay: 
         URI Template = string: http://%Domain%%Element%
         URI Parameters = map: 
           Domain = string: domain name
           Element = ref: Element/Name
         Dim = ref: wdata/model/dim/URI
         Dim Element = ref: Element/Name
         Level = ref: wdata/model/dim/Page View
         Group = ref: wdata/model/dim/Session
         Browser Height = int: browser height
     pos = v3d: (518, 202, 0)
     size = v3d: (810, 610, 0)
     titleBar = editor: 
       size = v3d: (61, 19, 0)
       text = string: 
   ```

1. 儲存檔案。
1. 要使此更改可供工作配置檔案的所有用戶使用，請在 [!DNL Profile Manager]中按一下右鍵列中 [!DNL .vw] 檔案的復 [!DNL User] 選標籤，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*。

   >[!NOTE]
   >
   >您可以為其他網站或子網域建立其他範本檔案。 您建立的每個範本都會出現在中 [!DNL Page Overlay menu]。

1. 在檔案的「上下文」 [!DNL Profile Manager]資料夾中，按一下右鍵檔案旁的複選標 [!DNL Page Overlay Link Templates.cfg] 記並按一下 **[!UICONTROL Make Local]**。

   此檔案的複選標籤將出現在列 [!DNL User] 中。

1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL from the workbench]**。
1. 以滑鼠右鍵按 **[!UICONTROL Link Templates]** 一下，然後按 **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**。
1. 視需要編輯LinkRegex向量的參數：

<table id="table_24DD4BB5009542F7BB1DA3318E2E6E2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對於此參數…… </th> 
   <th colname="col2" class="entry"> 提供此資訊…… </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>維度 </p> </td> 
   <td colname="col2"> <p>由連結表示的維（通常是下一個URI維）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>運算式 </p> </td> 
   <td colname="col2"> <p>用於選擇HTML連結相關部分以從「維」中查找下一個元素的規則運算式。 規則運算式必須完全符合，所要的輸出模式會以括弧分組。 如需規則運算式的詳細資訊，請參 <i>閱資料集設定指南</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>輸出模式 </p> </td> 
   <td colname="col2"> <p>用於提取Dimension參數的結果元素的規則運算式的輸出模式。 </p> </td> 
  </tr> 
 </tbody> 
</table>

下列範例檔案顯示三個規則運算式：

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. 要保存檔案，請按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部的，然後按一下 **[!UICONTROL Save]**。
1. 要使此更改可供工作配置檔案的所有用戶使用，請按一下右鍵列中的複選 [!DNL Page Overlay Link Templates.cfg] 標籤並 [!DNL User] 按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*。

