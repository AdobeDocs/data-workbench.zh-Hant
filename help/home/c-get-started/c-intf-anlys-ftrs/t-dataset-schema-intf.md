---
description: 變更預設視覺化的步驟。
solution: Analytics
title: 配置資料集模式介面
topic: Data workbench
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# 配置資料集模式介面{#configure-the-dataset-schema-interface}

變更預設視覺化的步驟。

將檔案新增至描述檔\*描述檔名稱*\Context\Dimension Legend folder of the Data Workbench server installation folder，即可控制在按一 [!DNL Dataset Schema Interface] 下維度名稱時顯示的視覺化類型。 此資 [!DNL Default.1d] 料夾中的檔案會控制所有維度的預設視覺化類型。 借由將維 *度名稱*.1d檔案(例如 [!DNL Hour.1d])新增至此資料夾，您可以控制該特定維度的預設視覺化。

如需詳細資訊， [!DNL Dataset Schema Interfaces]請參 [閱資料集架構介面](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)。

**若要變更預設視覺化**

1. 在任何工作區中，建立包含您要顯示在新預設視覺化中之資料的視覺化。

   例如，如果您想要將維度顯示在長條圖中，請建立長條圖視覺化，顯示所要的度量和維度。

1. 按一下右鍵註解窗口的上邊框，然後按一下 **[!UICONTROL Save]**。
1. 在視窗 [!DNL Save] 中，按一 ![](assets/btn_folder_up.png)下、連按兩 **[!UICONTROL Context]**&#x200B;下，然後按兩下 **[!UICONTROL Dimension Legend]**。
1. 在欄位 [!DNL File Name] 中，輸入維度名稱。

   The name of the [!DNL .1d] file must match the name of the dimension exactly. 例如, [!DNL Hour.1d].

1. 將副檔名變更為&quot;1d&quot;，然後按一下 **[!UICONTROL Save]**。

   檔案會儲存至使用者\*工作設定檔名稱*\Context\Dimension Legend folder。

   下次從中按一下該維度時，您指 [!DNL Dataset Schema Interface]定的視覺化隨即顯示。

1. （可選）要將此更改提供給工作配置檔案的所有用戶，請執行以下操作：

   1. 在中，單 [!DNL Profile Manager]擊，然 **[!UICONTROL Context]**&#x200B;後按一下 **[!UICONTROL Dimension Legend]**。

   1. 按一下右鍵列中新註解檔案名旁的複選標籤，然 [!DNL User] 後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*。

