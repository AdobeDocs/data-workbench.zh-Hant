---
description: 您可以定義新量度（稱為衍生量度），並使用量度編輯器編輯現有量度定義。
title: 使用衍生量度
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
exl-id: 83467c64-4b9a-44ab-91a2-202c76c89979
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# 使用衍生量度{#work-with-derived-metrics}

您可以定義新量度（稱為衍生量度），並使用量度編輯器編輯現有量度定義。

如需本節和[查詢語言語法](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)中提供之度量的詳細資訊，請參閱&#x200B;*度量、Dimension和篩選器指南*。

## 建立衍生量度{#section-d57b98bf0a9940daba4920ff7efc808d}

您可以使用[!DNL Metric Editor]來依名稱、公式和格式定義新度量，該度量將保存到User\*profile_name*\Metrics資料夾中，以備以後使用。

1. 使用&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Profile]**&#x200B;功能表選項，或對要建立度量的資料夾按一下右鍵&#x200B;**[!UICONTROL User]**&#x200B;欄，然後按一下&#x200B;**[!UICONTROL Create]** > **[!UICONTROL New Metric]**，開啟新的[!DNL Metric Editor]。

   將顯示[!DNL Metric Editor]。

1. 在「名稱」參數中，輸入新量度的名稱。

   請注意，底線(_)不允許使用空格()。 此外，您不能使用下列符號：

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. 在「公式」參數中，輸入新度量的運算式。 請注意，篩選器必須定義在括弧[內 ] 在運算式中。

   如需其他量度運算式語法規則，請參閱[量度運算式的語法](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66)。

   下表提供延伸量度的範例運算式。

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 延伸量度名稱 </th> 
      <th colname="col2" class="entry"> 運算式 </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>百分比第一個工作階段 </p> </td> 
      <td colname="col2"> <p><span class="filepath"> 會話[Session_Number="1"]/會話</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>轉換第一個工作階段 </p> </td> 
      <td colname="col2"> <p><span class="filepath"> 轉換[Session_Number="1"]</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>每位訪客的平均值 </p> </td> 
      <td colname="col2"> <p><span class="filepath"> 值/訪客</span> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
   >
   >輸入適當的運算式時，預覽行會顯示新量度的值。 如果運算式中有錯誤，預覽行會顯示錯誤訊息。

1. 按一下右鍵&#x200B;**[!UICONTROL (New)]**，然後按一下&#x200B;**[!UICONTROL Save]**。

   儲存量度時，代表新量度的檔案會在您的電腦上的Data Workbench安裝目錄\User\*設定檔名稱*\量度資料夾中建立。

   ![](assets/vis_MetricEditor_NewAndEditing.png)

您現在可以像選取任何內建量度一樣，在目前設定檔中使用新量度。 若要變更量度在量度功能表上的顯示順序，請參閱使用Order.txt檔案自訂功能表](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。[

如果您希望設定檔的所有使用者使用您建立的量度，必須使用[!DNL Profile Manager]將其發佈至工作設定檔。 請參閱[將檔案發佈至工作設定檔](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。

## 編輯衍生量度{#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. 在[!DNL Profile Manager]或[!DNL Metrics Manager]的&#x200B;*設定檔名稱*&#x200B;欄中，以滑鼠右鍵按一下您要編輯之量度檔案的勾號，然後按一下&#x200B;**[!UICONTROL Make Local]**。
1. 按一下右鍵[!DNL User]列中度量檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。

   >[!NOTE]
   >
   >您也可以以滑鼠右鍵按一下視覺效果中任何與量度相關的區域，以開啟[!DNL Metric Editor]以顯示量度功能表。 如需詳細資訊，請參閱[使用量度和Dimension功能表](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac)。

1. 在[!DNL Metric Editor]中，視需要使用[建立新衍生量度](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d)中的步驟2-4編輯並儲存量度定義。

   如果您希望設定檔的所有使用者使用您編輯的量度，則必須使用[!DNL Profile Manager]將其發佈至工作設定檔。 請參閱[將檔案發佈至工作設定檔](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。
