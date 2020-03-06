---
description: 本節說明如何在資料工作台中建立量度。
title: 量度設定
uuid: 57c1410b-c09c-4a59-b3a1-575323e1b8e3
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# 量度設定{#metrics-setup}

本節說明如何在資料工作台中建立量度。

## 瞭解量度 {#section-f0412e851fcb4ac9886dca4003d42cec}

量度是有關客戶活動的量化資訊，例如檢視、訂購、呼叫次數和收入。 量度是報告的基礎，有助於您檢視和理解資料關係。

「量度維度」可讓您依特定的「層級」來分組量度計數。 它也可讓您依特定層級將量度計數分組。

## 建立新量度 {#section-60a413899d1b4707965e06fb5ef7fc4e}

請依照下列步驟建立新量度：

1. 按一 **下工具** > **量度編輯器**。

1. 在量度編輯器中，輸入新的量度名稱和公式。 ![](assets/dwb_impl_metrics1.png)

1. 儲存至「量度」資料夾。 ![](assets/dwb_impl_metrics2.png)

## 建立和編輯衍生量度 {#section-ebdcd3ec652f485e90e001d694eab6d0}

使用量度編輯器可依名稱、公式和格式定義新量度，並儲存至資料夾以 [!DNL User\profile_name\Metrics] 供日後使用。

1. 使用「管理>描述檔 **」功能表選項，或以滑鼠右鍵按一下您要建立量度之資料夾的「使用者」欄，然後按一下「建立>新** 建量度」，以開啟新的量度編輯器 ****。 隨即顯示量度編輯器。

1. 在「名 *稱* 」參數中，輸入新度量的名稱。

   >[!NOTE]
   >
   >請注意，允許空格()，而下划線(_)則不允許。 此外，您不能使用下列符號：+ - * /

   ![](assets/dwb_impl_metrics3.png)

1. 在「公 *式* 」參數中，輸入新度量的運算式。

   >[!NOTE]
   篩選器必須定義在方括弧內 [ ] 中。 如需其他度量運算式語法規則，請參 [閱度量運算式的語法。](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

   此表格提供擴充度量的範例運算式。 ![](assets/dwb_impl_metrics4.png)

   >[!NOTE]
   輸入適當的運算式時，預覽行會顯示新量度的值。 如果運算式中有錯誤，預覽行會顯示錯誤訊息。

1. 按一下右鍵並選擇「 **保存**」。 儲存量度時，代表新量度的檔案會在您的電腦上，在DWB安裝目錄\User\profile name\Metrics資 *料夾中建立* 。

## 編輯現有衍生量度 {#section-4b5b7baf885b45cc8b358d1bd774e925}

1. 在「描述檔管理員」或「量度管理員」的描述檔名稱欄中，以滑鼠右鍵按一下您要編輯的量度檔案的勾號，然後按一下「設為本機」 ****。
1. 在「使用者」欄中，以滑鼠右鍵按一下量度檔案的核取標籤，然後從工作台按 **一下** 「開啟」。

   >[!NOTE]
   您也可以在視覺化中以滑鼠右鍵按一下任何與度量相關的區域，以顯示度量功能表，以開啟度量編輯器。

1. 在量度 **編輯器中**，使用建立新衍生量度的步驟2-4，視需要編輯 *和儲存量度定義*。

   如果您希望該描述檔的所有使用者都使用您編輯的度量，則必須使用「描述檔管理員」將其發佈至工作描述檔。

如需詳細協助，請參閱檔案：

[量度運算式的語法](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

[建立和編輯衍生量度](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/profile-mgr/c-drvd-mtrcs.html)
