---
description: 變更預設視覺化的步驟。
title: 設定資料集結構介面
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# 設定資料集結構介面{#configure-the-dataset-schema-interface}

變更預設視覺化的步驟。

當您按一下[!DNL Dataset Schema Interface]中的維度名稱時，您可以將檔案新增至描述檔\*描述檔名稱*\Context\Dimension Legend folder of the Data Workbench server installation folder，以控制顯示哪種視覺化類型。 此資料夾中的[!DNL Default.1d]檔案會控制所有維度的預設視覺化類型。 借由將&#x200B;*維度名稱*.1d檔案（例如[!DNL Hour.1d]）新增至此資料夾，您可以控制該特定維度的預設視覺化。

有關[!DNL Dataset Schema Interfaces]的詳細資訊，請參閱[資料集模式介面](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)。

**若要變更預設視覺化**

1. 在任何工作區中，建立包含您要顯示在新預設視覺化中之資料的視覺化。

   例如，如果您想要將維度顯示在長條圖中，請建立長條圖視覺化，顯示所要的度量和維度。

1. 按一下右鍵註解窗口的上邊框，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Save]視窗中，按一下![](assets/btn_folder_up.png)，按兩下&#x200B;**[!UICONTROL Context]**，然後按兩下&#x200B;**[!UICONTROL Dimension Legend]**。
1. 在[!DNL File Name]欄位中，輸入維度名稱。

   [!DNL .1d]檔案的名稱必須與維的名稱完全匹配。 例如：[!DNL Hour.1d]。

1. 將副檔名變更為&quot;1d&quot;，然後按一下&#x200B;**[!UICONTROL Save]**。

   檔案會儲存至使用者\*工作設定檔名稱*\Context\Dimension Legend folder。

   下次從[!DNL Dataset Schema Interface]中按一下該維度時，會顯示您指定的視覺化。

1. （可選）要將此更改提供給工作配置檔案的所有用戶，請執行以下操作：

   1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Context]** ，然後按一下&#x200B;**[!UICONTROL Dimension Legend]**。

   1. 按一下右鍵[!DNL User]列中新註解檔案名旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL working profile name]**>*。
