---
description: 您可以定義新量度（稱為衍生量度），並使用量度編輯器編輯現有量度定義。
solution: Analytics
title: 使用衍生量度
topic: Data workbench
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使用衍生量度{#work-with-derived-metrics}

您可以定義新量度（稱為衍生量度），並使用量度編輯器編輯現有量度定義。

如需本節和查詢語言語法中提供之度量的詳細資訊 [，請參](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)閱度量、維度和篩選指南 **。

## 建立衍生量度 {#section-d57b98bf0a9940daba4920ff7efc808d}

您可以使 [!DNL Metric Editor] 用名稱、公式和格式來定義新量度，此量度會儲存至User\*profile_name*\Metrics資料夾以供日後使用。

1. 使用「 [!DNL Metric Editor] > **[!UICONTROL Admin]** 功能表」選項，或以滑鼠右鍵按一 **[!UICONTROL Profile]** 下您要建立量度之資料夾的欄，然後按一下「 **[!UICONTROL User]** >」 **[!UICONTROL Create]****[!UICONTROL New Metric]**&#x200B;以開啟。

   顯示 [!DNL Metric Editor] 器。

1. 在「名稱」參數中，輸入新量度的名稱。

   請注意，允許空格()，而下划線(_)則不允許。 此外，您不能使用下列符號：

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. 在「公式」參數中，輸入新度量的運算式。 請注意，篩選器必須定義在方括弧內 [ ] 中。

   如需其他度量運算式語法規則，請參 [閱度量運算式的語法](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66)。

   下表提供擴充量度的範例運算式。

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 延伸量度名稱 </th> 
      <th colname="col2" class="entry"> 運算式 </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>首次作業百分比 </p> </td> 
      <td colname="col2"> <p><span class="filepath"> 會話[Session_Number="1"]/會話</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>轉換第一階段作業 </p> </td> 
      <td colname="col2"> <p><span class="filepath"> 轉換[Session_Number="1"]</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>每位訪客的平均值 </p> </td> 
      <td colname="col2"> <p><span class="filepath"> 值／訪客</span> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
   >
   >輸入適當的運算式時，預覽行會顯示新量度的值。 如果運算式中有錯誤，預覽行會顯示錯誤訊息。

1. 按一下滑鼠右 **[!UICONTROL (New)]** 鍵並按一下 **[!UICONTROL Save]**。

   儲存量度時，代表新量度的檔案會在您的電腦上建立在「資料工作台安裝目錄\User\*描述檔名稱*\Metrics資料夾」。

   ![](assets/vis_MetricEditor_NewAndEditing.png)

您現在可以像選擇任何內建度量一樣，在目前的描述檔中使用新度量。 若要變更量度在量度功能表上的顯示順序，請參閱使 [用Order.txt檔案自訂功能表](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。

如果您希望該描述檔的所有使用者都使用您建立的度量，您必須使用發佈至使用的工作描述檔 [!DNL Profile Manager]。 請參 [閱將檔案發佈至您的工作設定檔](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。

## 編輯衍生量度 {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. 在或 [!DNL Profile Manager] 的 [!DNL Metrics Manager]描述檔名 *稱欄中* ，以滑鼠右鍵按一下您要編輯之量度檔案的核取標籤，然後按一下 **[!UICONTROL Make Local]**。
1. 以滑鼠右鍵按一下欄中量度檔案的核取標籤， [!DNL User] 然後按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。

   >[!NOTE]
   >
   >您也可以在視覺化 [!DNL Metric Editor] 中以滑鼠右鍵按一下任何與度量相關的區域，以顯示度量功能表。 如需詳細資訊，請參 [閱使用量度和維度功能表](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac)。

1. 在中， [!DNL Metric Editor]使用「建立新衍生量度」中的步驟2-4，視需要編輯 [及儲存量度定義](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d)。

   如果您希望該描述檔的所有使用者都使用您編輯的度量，您必須使用發佈至使用的工作描述檔 [!DNL Profile Manager]。 請參 [閱將檔案發佈至您的工作設定檔](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。

