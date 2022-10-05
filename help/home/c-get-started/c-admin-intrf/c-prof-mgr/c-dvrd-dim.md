---
description: 您使用Data Workbench建立的新維度（稱為衍生維度）為用戶端維度。
title: 使用衍生維度
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# 使用衍生維度{#work-with-derived-dimensions}

{{eol}}

您使用Data Workbench建立的新維度（稱為衍生維度）為用戶端維度。

在資料集建置和更新程式期間，您不必定義這些維度(在 [!DNL Transformation.cfg] 檔案)，衍生維度會以 [!DNL .dim] 檔案。 因此，您可以變更現有維度並建立新的衍生維度，而不需重新處理資料集。

>[!NOTE]
>
>如需本節中提供之維度的詳細資訊，請參閱適當的Data Workbench應用程式指南。

如需資料集設定和更新程式的詳細資訊，請參閱 *資料集組態指南*.

## 建立衍生維度 {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

若要建立衍生維度，您可以複製和修改現有維度，或從視覺效果中儲存維度。

## 從現有維度建立衍生維度 {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

使用者最常想從現有維度建立新的時間維度。 例如，您可以從現有的「最近7天」維度建立新的「最近5天」維度。

1. 在 [!DNL Profile Manager]，在 *設定檔名稱* 欄中，按一下右鍵與要建立的維相似的維的複選標籤，然後按一下 **[!UICONTROL Copy]**.

   例如，若要複製 [!DNL Last 7 Days.dim] 從 [!DNL Traffic] 設定檔中，請以滑鼠右鍵按一下 [!DNL Traffic] 欄，按一下 **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. 在 [!DNL User] 欄，在其中儲存複製的維，然後按一下 **[!UICONTROL Paste]**.

   維度會顯示在選取的「Dimension」資料夾中，並在 [!DNL User] 欄。

1. 要更名新維，請在 [!DNL User] 欄，並在 [!DNL File] 欄位。
1. 在滑鼠右鍵功能表中，按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 尺寸的定義參數隨即出現。
1. 根據需要修改參數以定義新尺寸。

   若是時間維度，您最可能只需要修改「計數」和「範圍」參數。

1. 若要儲存檔案，請按一下滑鼠右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   如果您希望某個設定檔的所有使用者使用您建立的維度，必須將其上傳至使用 [!DNL Profile Manager]. 如需詳細資訊，請參閱 [將檔案發佈至工作設定檔](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

您現在可以在目前設定檔中使用新維度，方法是選取新維度，就像選取任何內建維度一樣。

## 從視覺效果儲存維度 {#section-84cfe5e9ccb640afa2ee4e2da2682757}

您可以從程式圖和區段中儲存延伸維度。 如需從程式圖中儲存維度的步驟，請參閱 [從流程圖中保存Dimension](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). 如需儲存區段維度的步驟，請參閱 [建立區段Dimension](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) 在82頁。

## 將區段儲存為維度 {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

您也可以將定義的區段儲存為維度。 如需步驟，請參閱 [重複使用區段視覺效果](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## 編輯現有的派生維 {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   n [!DNL Profile Manager]，在 *設定檔名稱* 欄，按一下右鍵要編輯的維檔案的複選標籤，然後按一下 **[!UICONTROL Make Local]**.
1. 按一下右鍵中維檔案的複選標籤 [!DNL User] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. 視需要完成參數。 如需詳細資訊，請連絡Adobe諮詢服務。
1. 若要儲存檔案，請按一下滑鼠右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   如果您希望某個設定檔的所有使用者使用修改的維度，您必須使用 [!DNL Profile Manager]. 如需詳細資訊，請參閱 [將檔案發佈至工作設定檔](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
