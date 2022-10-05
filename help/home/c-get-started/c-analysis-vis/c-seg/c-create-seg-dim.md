---
description: 若要建立區段維度，請先在工作區中進行選取，然後將區段新增至視覺效果。
title: 建立區段維度
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
exl-id: 393d544e-e821-49e3-8cfb-5a3496aa7380
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 3%

---

# 建立區段維度{#create-a-segment-dimensions}

{{eol}}

若要建立區段維度，請先在工作區中進行選取，然後將區段新增至視覺效果。

**若要建立區段維度**

1. 將區段視覺效果新增至工作區。 例如：

   ![](assets/vis_Segment.png)

1. 將視覺效果新增至您的工作區，供您用來定義區段，然後進行所需的選取以定義您的區段。
1. 在區段視覺效果中，以滑鼠右鍵按一下您要新增新區段的區段標籤，然後按一下 **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >若要建立新的第一個區段，請以滑鼠右鍵按一下 **[!UICONTROL Segments]** 標籤並按一下 **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   視覺效果中會出現新區段（名為「新區段」）。 「其他」區段代表未包含在您定義區段中的所有資料：這實際上是資料集資料和區段資料之間的差異。

1. 以滑鼠右鍵按一下新建立的區段，然後按一下 **[!UICONTROL Rename Segment]**.
1. 在名稱欄位中，為新區段輸入描述性名稱。

   >[!NOTE]
   >
   >如果量度值，例如 [!DNL Site]，且符合多個區段的條件，則量度值只會包含在第一個列出的相符區段中。

**儲存區段維度的方式**

1. 以滑鼠右鍵按一下「區段」標籤，然後按一下 **[!UICONTROL Save Dimension]**. 此 [!DNL Save Dimension As] 的上界。 預設的保存位置是User\*profile name*\Dimension資料夾。
1. 在 [!DNL File name] 欄位，為要儲存為維度的區段輸入描述性名稱，然後按一下 **[!UICONTROL Save]**.

每當您使用視覺效果時，都可以存取區段維度。 您也可以使用區段匯出功能，匯出與儲存維度中的元素相關聯的資料。

如需區段匯出功能的詳細資訊，以及視需要設定該功能的指示，請參閱 [設定要匯出的區段](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
