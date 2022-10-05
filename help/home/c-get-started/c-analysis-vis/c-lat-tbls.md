---
description: 延時表格視覺效果是包含延時維度的表格，延時維度是一種衍生維度，可測量自特定事件發生後經過的時間。
title: 延遲表
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
exl-id: 22f6d52f-e1c2-430a-9e69-3440be0ecdea
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 1%

---

# 延遲表{#latency-tables}

{{eol}}

延時表格視覺效果是包含延時維度的表格，延時維度是一種衍生維度，可測量自特定事件發生後經過的時間。

您可以在一或多個視覺效果內進行選取，並使用「設定事件」內容功能表選項將這些選取項目設為事件，借此定義事件。 延遲表格對於追蹤與促銷活動或您尋找時間關聯的特定客戶順序相關的活動特別有用。

在 [!DNL Site]，延時表格會提供事件前或之後最多七天所發生之訪客工作階段的相關資訊，但您可以設定延時表格，以提供不同可計數和時間維度的相關資訊。 請參閱 [配置延遲表](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c).

上層維度的元素（例如工作階段）屬於您選取的特定事件，其延遲為零。 所有其他元素都會被指派延遲，以反映與事件的距離（在適當的時間維度中）。

以下範例說明如何使用延遲表格。

**識別與促銷活動相關的值事件**

假設您想追蹤客戶在回應特定廣告促銷活動前後七天的活動。 若要檢視特定廣告促銷活動的延遲，您可將感興趣的促銷活動設定為延遲表格的事件。

以下工作區中的延遲是根據選取的促銷活動11566（回應此促銷活動的工作階段）而定。

![](assets/vis_Latency.png)

「+0天」的延遲可識別回應Campaign 11566的工作階段，以及同一天發生的相同客戶的所有其他工作階段。

延遲「–2天」可識別在客戶回應促銷活動前兩天，所發生的相同客戶的工作階段。

「+7天」的延遲可識別在客戶回應促銷活動七天後所發生的工作階段。

除了下面幾節中列出的過程外，您還可以執行表格中可以執行的所有相同任務，如排序元素、遮色片元素、添加系列圖例、導出資料等。 如需詳細資訊，請參閱 [表格](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## 建立延遲表 {#section-31a03031d9854ef7acc2462d4f37678d}

若要建立延遲表格，請先選取該選取項目，然後將該選取項目設為您要追蹤延遲的事件。

1. 在工作區中按一下滑鼠右鍵，然後開啟所需的視覺效果，視覺效果必須以用來設定延遲表格的可數維度為基礎。

   例如，在 [!DNL Site] 視覺效果必須以工作階段為基礎。

1. 開啟空白的延遲表格。
1. 在工作區中進行選取。
1. 在延遲表格內按一下滑鼠右鍵，然後按一下 **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>除非您將選取的項目儲存為延遲維度，否則您選取的事件不會持續存在。 如需步驟，請參閱 [重複使用延遲Dimension](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46).

## 重複使用延遲表 {#section-05f741169d204213b6537dce553e4f73}

如果您想再次使用相同的延遲表，可以將延遲表保存在本地，或者如果您擁有適當的權限，可以將該延遲表保存到伺服器，以便特定配置檔案的所有用戶訪問。

**儲存延遲表格以用於其他工作區的方式**

1. 以滑鼠右鍵按一下視覺效果的上方邊框，然後按一下 **[!UICONTROL Save]**. 此 [!DNL Save] 的上界。 預設保存位置為User\*profile name*\Work資料夾。
1. 在 [!DNL File name] 欄位，輸入視覺效果的描述性名稱，然後按一下 **[!UICONTROL Save]**.

**檢索保存的延遲表**

1. 在工作區中按一下滑鼠右鍵，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL File]**. 此 [!DNL Open Visualization] 的上界。
1. 導覽至您儲存的延遲表格。
1. 選取延時表格視覺效果檔案( [!DNL *.vw])，然後按一下 **[!UICONTROL Open]**.

## 重複使用延遲維度 {#section-29c6483bf9ba476fb1c24ad1df253f46}

如果您想再次使用相同的延遲維度，可以將延遲維度儲存在本機，或如果您擁有適當權限，則可將延遲維度儲存至伺服器，供特定設定檔的所有使用者存取。

您建立的任何延遲維都會儲存在設定檔的「Dimension」目錄中，並可在 [!DNL Change Dimension] Data Workbench內的下拉式清單。

**儲存延遲維度以用於其他工作區的方式**

1. 以滑鼠右鍵按一下 [!DNL Latency] 欄標籤或其元素之一，然後按一下 **[!UICONTROL Save Dimension]**. 此 [!DNL Save Dimension As] 的上界。
1. 在Dimension目錄中選擇或建立適當的子目錄。
1. 在 [!DNL File name] 欄位，為維度輸入描述性名稱(例如 [!DNL Latency for Campaign 11565.dim])，然後按一下 **[!UICONTROL Save]**.

**擷取儲存的延遲維度**

1. 在工作區中按一下滑鼠右鍵，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL File]**. 此 [!DNL Open Visualization] 的上界。
1. 導覽至您儲存在「使用者」\*設定檔名稱*\Dimension」資料夾中的延遲視覺效果。
1. 選取延遲維度檔案( [!DNL *.dim])，然後按一下 **[!UICONTROL Open]**.

## 匯出至 Microsoft Excel {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

有關導出窗口的資訊，請參見 [導出窗口資料](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).

## 匯出至 TSV 檔案 {#section-fd921f351c994ed0a94f63d3bd5b5a87}

有關導出窗口的資訊，請參見 [導出窗口資料](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
