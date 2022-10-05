---
description: 變更預設視覺效果的步驟。
title: 設定資料集結構介面
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# 設定資料集結構介面{#configure-the-dataset-schema-interface}

{{eol}}

變更預設視覺效果的步驟。

您可以控制在 [!DNL Dataset Schema Interface] 將檔案添加到Data Workbench伺服器安裝資料夾的「配置檔案」\*profile name*\Context\Dimension圖例資料夾。 此 [!DNL Default.1d] 此資料夾中的檔案會控制所有維度的預設視覺效果類型。 借由新增 *維度名稱*.1d檔案(如 [!DNL Hour.1d])，您可以控制該特定維度的預設視覺效果。

如需 [!DNL Dataset Schema Interfaces]，請參閱 [資料集結構介面](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**若要變更預設視覺效果**

1. 在任何工作區中，建立包含您要顯示在新預設視覺效果中之資料的視覺效果。

   例如，如果您想要將維度顯示在橫條圖中，請建立橫條圖視覺效果以顯示所需的量度和維度。

1. 按一下右鍵標注窗口的上邊框，然後按一下 **[!UICONTROL Save]**.
1. 在 [!DNL Save] 按一下 ![](assets/btn_folder_up.png)，按兩下 **[!UICONTROL Context]**，然後按兩下 **[!UICONTROL Dimension Legend]**.
1. 在 [!DNL File Name] 欄位中輸入維名稱。

   的名稱 [!DNL .1d] 檔案的名稱必須與維度的名稱完全相符。 例如，[!DNL Hour.1d]。

1. 將副檔名變更為「1d」，然後按一下 **[!UICONTROL Save]**.

   檔案將保存到「用戶」\*「工作配置檔案名」*\「上下文」\「Dimension圖例」資料夾。

   下次在 [!DNL Dataset Schema Interface]，則會顯示您指定的視覺效果。

1. （選用）若要讓工作設定檔的所有使用者都能使用此變更：

   1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Context]**，然後按一下 **[!UICONTROL Dimension Legend]**.

   1. 按一下右鍵新標注的檔案名旁的複選標籤(位於 [!DNL User] 欄，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
