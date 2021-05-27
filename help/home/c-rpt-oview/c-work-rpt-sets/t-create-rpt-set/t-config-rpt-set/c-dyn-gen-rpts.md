---
description: 您可以為您在查閱檔案中指定的維度元素或特定數量的維度元素（例如擁有10個最高順序計數的使用者）動態產生報表。
title: 動態產生報表
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
exl-id: c14d93cd-212d-44a1-aff9-652e5c4fbda0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 1%

---

# 動態產生報表{#dynamically-generating-reports}

您可以為您在查閱檔案中指定的維度元素或特定數量的維度元素（例如擁有10個最高順序計數的使用者）動態產生報表。

>[!NOTE]
>
>Adobe不鼓勵建立動態報表集以用於每日（或更頻繁）產生報表。 如果您使用大型或複雜查詢來設定報表，動態報表產生可能會耗用大量資源。

* [查閱檔案Dimension元素報表](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [排名在前的Dimension元素報表](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## 查閱檔案Dimension元素報表{#section-a5e8f38af06c42b4bfddec4bafbf03d6}

要配置報表集以動態生成和（可選）分發查找檔案中指定的維元素的報表，請在[!DNL Report.cfg]檔案中指定以下參數：

* [!DNL Dimension Name]
* [!DNL Lookup File]

如需這些參數的詳細說明，請參閱[Report.cfg參數](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

**若要使用查閱檔案建立動態報表集**

1. 為指定維度建立兩欄查閱檔案。 此檔案必須包含兩個以Tab分隔的欄，不含標題列。

   * 第1欄應包含維度元素清單。
   * 第2欄應包含報表收件者的電子郵件地址。 第1欄中特定元素的報表會傳送至第2欄中同一列的電子郵件地址。 您可以用逗號分隔多個電子郵件地址（不含空格）。

      >[!NOTE]
      >
      >
      >    
      >    
      >    * 如果報表不要以電子郵件傳送，第2欄可以是空白的，但必須存在。
      >    * 此檔案可能包含空行。




1. 選填。若要啟用報表的電子郵件傳送，您必須在該特定報表集之[!DNL Report.cfg]檔案的[!DNL Mail Report]區段中執行下列動作：

   * 在SMTP伺服器參數中，列出要用於通過電子郵件分發報告的適當SMTP伺服器。
   * 在「收件者」參數中，列出至少一個電子郵件地址，以便透過電子郵件分發報表。 系統不會將報表寄送至列出的地址，您只會設定此參數，以允許以電子郵件傳送報表。 這可能是偽地址，但必須是允許的格式（例如[!DNL jsmith@company.com]）。

1. 將查閱檔案儲存至報表集的資料夾。
1. 開啟報表集的[!DNL Report.cfg]檔案。
1. 在「Dimension名稱」參數中，輸入您要動態產生報表的維度名稱。
1. 在「查閱檔案」參數中，輸入查閱檔案的位置和名稱，該檔案包含您要納入報表的維度元素以及收件者電子郵件地址。
1. 對其他報表集重複這些步驟。

>[!NOTE]
>
>整個報表集完成前，動態報表不會以電子郵件傳送給收件者。

## 排名在前的Dimension元素報表{#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

若要設定報表集以動態產生排名最前的維度元素報表（依指定的量度計算），請在[!DNL Report.cfg]檔案中指定下列參數：

* 維度名稱
* 前N個量度
* 前N個值
* （可選）預載查詢篩選器

如需這些參數的詳細說明，請參閱[Report.cfg參數](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

**為排名最前的元素建立動態報表集**

1. 開啟報表集的[!DNL Report.cfg]檔案。
1. 在「Dimension名稱」參數中，輸入您要動態產生報表集的維度名稱。
1. 在前N個量度參數中，輸入您要依其排序維度的量度名稱。
1. 在前N個值參數中，輸入您要在報表集中的維度元素數量。
1. （選用）在「預先載入查詢篩選器」參數中，輸入所需篩選器的名稱。
1. 對其他報表集重複這些步驟。
1. 如需如何將動態標題視覺效果與報表搭配使用的資訊，請參閱&#x200B;*Data Workbench使用手冊*。
