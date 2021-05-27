---
description: 變更預設視覺效果的步驟。
title: 設定資料集結構介面
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# 設定資料集結構介面{#configure-the-dataset-schema-interface}

變更預設視覺效果的步驟。

您可以將檔案新增至設定檔\*設定檔名稱*\Context\Dimension Legend folder of the Data Workbench server installation folder ，以控制當您按一下[!DNL Dataset Schema Interface]中的維度名稱時顯示的視覺效果類型。 此資料夾中的[!DNL Default.1d]檔案會控制所有維度的預設視覺效果類型。 將&#x200B;*維度名稱*.1d檔案（例如[!DNL Hour.1d]）新增至此資料夾，即可控制該特定維度的預設視覺效果。

如需[!DNL Dataset Schema Interfaces]的詳細資訊，請參閱[資料集結構介面](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)。

**若要變更預設視覺效果**

1. 在任何工作區中，建立包含您要顯示在新預設視覺效果中之資料的視覺效果。

   例如，如果您想要將維度顯示在橫條圖中，請建立橫條圖視覺效果以顯示所需的量度和維度。

1. 按一下右鍵標注窗口的上邊框，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Save]窗口中，按一下![](assets/btn_folder_up.png)，按兩下&#x200B;**[!UICONTROL Context]**，然後按兩下&#x200B;**[!UICONTROL Dimension Legend]**。
1. 在[!DNL File Name]欄位中，輸入維度名稱。

   [!DNL .1d]檔案的名稱必須與維的名稱完全匹配。 例如：[!DNL Hour.1d]。

1. 將副檔名變更為「1d」，然後按一下&#x200B;**[!UICONTROL Save]**。

   檔案將保存到用戶\*工作配置檔案名*\Context\Dimension Legend folder。

   下次在[!DNL Dataset Schema Interface]中按一下該維度時，會顯示您指定的視覺效果。

1. （選用）若要讓工作設定檔的所有使用者都能使用此變更：

   1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Context]**，然後按一下&#x200B;**[!UICONTROL Dimension Legend]**。

   1. 在[!DNL User]列中按一下右鍵新標注的檔案名旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*。
