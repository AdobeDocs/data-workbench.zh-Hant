---
description: 您使用「資料工作台」建立的新維度（稱為衍生維度）為用戶端維度。
solution: Analytics
title: 使用衍生維度
topic: Data workbench
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使用衍生維度{#work-with-derived-dimensions}

您使用「資料工作台」建立的新維度（稱為衍生維度）為用戶端維度。

在資料工作台伺服器電腦的資料集建構和更新程式(在檔案中 [!DNL Transformation.cfg] )中，衍生維度不是定義這些維度，而是個別建立並儲存為描述檔 [!DNL .dim] 中的檔案。 因此，您可以變更現有維度並建立新的衍生維度，而不需重新處理資料集。

>[!NOTE]
>
>如需本節中提供之維度的詳細資訊，請參閱適當的資料工作台應用程式指南。

如需資料集設定和更新程式的詳細資訊，請參閱資料集 *設定指南*。

## 建立派生維 {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

若要建立衍生維度，您可以複製和修改現有維度，或從視覺化中儲存維度。

## 從現有維建立派生維 {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

使用者最常想從現有維度建立新的時間維度。 例如，您可以從現有的「最近7天」維度建立新的「最近5天」維度。

1. 在的 [!DNL Profile Manager]配置檔案名 *稱列中* ，按一下右鍵要建立的維的複選標籤，然後按一下 **[!UICONTROL Copy]**。

   例如，要從配置檔案的 [!DNL Last 7 Days.dim] 「報告」資料夾復 [!DNL Traffic] 制檔案，請按一下右鍵列中檔案名的複選標 [!DNL Traffic] 記，然後按一下 **[!UICONTROL Copy]**。

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. 在要儲存復 [!DNL User] 制維的資料夾的列中按一下右鍵，然後按一下 **[!UICONTROL Paste]**。

   維將顯示在選定的「維」資料夾中，並在列中加上複選 [!DNL User] 標籤。

1. 要更名新維，請在列中按一下右鍵其複選標 [!DNL User] 記，然後在欄位中鍵入新名 [!DNL File] 稱。
1. 在右鍵功能表中，按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 此時將顯示尺寸的定義參數。
1. 根據需要修改參數以定義新尺寸。

   對於時間維度，您最可能只需要修改「計數」和「範圍」參數。

1. 要保存檔案，請按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部的，然後按一下 **[!UICONTROL Save]**。

   如果您希望某個配置檔案的所有用戶都使用您建立的維，則必須使用將其上載到配置檔案 [!DNL Profile Manager]。 如需詳細資訊，請參 [閱「將檔案發佈至您的工作設定檔](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)」。

現在，您可以像選擇任何內置維一樣，在當前配置檔案中使用新維。

## 從視覺化儲存維度 {#section-84cfe5e9ccb640afa2ee4e2da2682757}

您可以從流程映射和區段儲存延伸維度。 有關從流程映射中保存維的步驟，請參閱從 [流程映射中保存維](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051)。 如需儲存區段維度的步驟，請參 [閱第](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) 82頁的建立區段維度。

## 將區段儲存為維度 {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

您也可以將定義的區段儲存為維度。 如需步驟，請參 [閱重複使用區段視覺化](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc)。

## 編輯現有派生維 {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   在 [!DNL Profile Manager]配置檔案名 *稱列中* ，按一下右鍵要編輯的維檔案的複選標籤，然後按一下 **[!UICONTROL Make Local]**。
1. 按一下右鍵列中維檔案的複選標籤， [!DNL User] 然後按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。
1. 視需要填寫參數。 如需詳細資訊，請聯絡Adobe諮詢服務。
1. 要保存檔案，請按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部的，然後按一下 **[!UICONTROL Save]**。

   如果您希望某個配置檔案的所有用戶都使用修改的維，則必須使用將其上載到配置檔案 [!DNL Profile Manager]。 如需詳細資訊，請參 [閱「將檔案發佈至您的工作設定檔](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)」。

