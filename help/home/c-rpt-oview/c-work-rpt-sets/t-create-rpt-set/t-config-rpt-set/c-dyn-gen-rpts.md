---
description: 您可以動態產生您在查閱檔案中指定的維度元素或特定數目的維度元素的報表，例如為擁有10個最高順序計數的使用者。
solution: Analytics
title: 動態產生報表
topic: Data workbench
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 動態產生報表{#dynamically-generating-reports}

您可以動態產生您在查閱檔案中指定的維度元素或特定數目的維度元素的報表，例如為擁有10個最高順序計數的使用者。

>[!NOTE]
>
>Adobe不建議建立動態報表集，以產生每日（或更頻繁）的報表。 如果您使用大型或複雜的查詢來設定報表，動態報表產生可能會耗用大量資源。

* [查閱檔案維度元素報表](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [排名最前的維度元素報表](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## 查閱檔案維度元素報表 {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

若要設定報表集以動態產生和（選擇性）分發查閱檔案中指定之維度元素的報表，請在檔案中指定下列參 [!DNL Report.cfg] 數：

* [!DNL Dimension Name]
* [!DNL Lookup File]

如需這些參數的詳細說明，請參 [閱Report.cfg參數](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

**若要使用查閱檔案建立動態報表集**

1. 為指定維度建立雙欄查閱檔案。 此檔案必須包含兩個以Tab分隔的欄，不含標題列。

   * 列1應包含維元素清單。
   * 第2欄應包含報表收件者的電子郵件地址。 第1欄中指定元素的報表會傳送至第2欄中同一列的電子郵件地址。 您可以用逗號分隔多個電子郵件地址（無空格）。

      >[!NOTE]
      >
      >
      >    
      >    
      >    * 如果報表不以電子郵件傳送，則欄2可以是空的，但必須存在。
      >    * 此檔案可能包含空行。




1. 選填。若要啟用報表的電子郵件傳送，您必須在該特定報表集 [!DNL Mail Report] 的檔案 [!DNL Report.cfg] 區段中執行下列動作：

   * 在「SMTP伺服器」參數中，列出要用於通過電子郵件分發報告的適當SMTP伺服器。
   * 在「收件者」參數中，列出至少一個電子郵件地址，以便透過電子郵件分發報表。 報表不會郵寄至所列的位址——您只設定此參數，才允許以電子郵件傳送報表。 這可以是偽造地址，但必須是允許的格式(例如 [!DNL jsmith@company.com])。

1. 將查閱檔案儲存至報表集的資料夾。
1. 開啟報 [!DNL Report.cfg] 表集的檔案。
1. 在「維度名稱」參數中，輸入您要動態產生報表的維度名稱。
1. 在「查閱檔案」參數中，輸入查閱檔案的位置和名稱，該檔案包含您要在報表和收件者電子郵件地址中的維度元素。
1. 重複這些步驟以取得其他報表集。

>[!NOTE]
>
>在完成整個報表集之前，動態報表不會以電子郵件寄送給收件者。

## 排名最前的維度元素報表 {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

若要設定報表集為動態產生排名最前的維度元素報表，請依指定的量度計算，在檔案中指定下列參 [!DNL Report.cfg] 數：

* 維度名稱
* 前N個量度
* 前N個值
* （可選）預先載入查詢篩選

如需這些參數的詳細說明，請參 [閱Report.cfg參數](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

**若要建立頂層元素的動態報表集**

1. 開啟報表集的檔 [!DNL Report.cfg] 案。
1. 在「維度名稱」參數中，輸入您要動態產生報表集的維度名稱。
1. 在前N個量度參數中，輸入您要依此量度排序維度的量度名稱。
1. 在「前N個值」參數中，輸入您要在報表集中輸入的維度元素數目。
1. （可選）在「預先載入查詢篩選」參數中，輸入所要篩選的名稱。
1. 重複這些步驟以取得其他報表集。
1. 如需將動態標題視覺化用於報表的詳細資訊，請參閱「資 *料工作台使用指南」*。

