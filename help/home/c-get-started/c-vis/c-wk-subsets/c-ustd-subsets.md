---
description: 關於子集的概念資訊。
title: 瞭解子集
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
exl-id: a75b36f9-d34d-4a4a-8a2c-15ae5461823c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# 瞭解子集{#understanding-subsets}

{{eol}}

關於子集的概念資訊。

使用子集時，請記住以下事項：

* 所有基準現在都與您的子集相關，而非與整個資料集相關，在分析特定子集時更實用。 請參閱 [了解基準](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* 使用子集會影響所有工作區，因為子集會全域套用至Data Workbench。
* 子集只影響度量和非正規維，不影響正常維。
* 使用時 [!DNL Report]，子集不會影響已發佈供其他人檢視的報表中的資料。
* 套用後，您的子集將對設定檔中所有後續工作生效，包括下次開啟此Data Workbench例項時，直到您將其移除為止。
* 表示已套用子集的唯一位置是您在工作區中按一下滑鼠右鍵所觸及的內容功能表。

   ![](assets/mnu_Subset.png)

* 您必須聯機工作才能更改或刪除子集。 如果您離線工作且已套用子集，則無法檢視整個資料集的結果。 請參閱 [離線和線上工作](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >子集的大小受限於駐留在單一Data Workbench伺服器上的篩選器中的資料量。 因此，如果資料集涵蓋Data Workbench伺服器叢集，則子集的資料僅來自叢集中的一個Data Workbench伺服器。

大型零售商的使用者想要建立特定工作周資料的子集（本機快取），然後僅對該周資料執行查詢。 為此，使用者會建立地標的子集。

下列範例顯示一段時間內的訪客長條圖和流量量度圖例。 第一個圖沒有選擇：資料集中的所有資料都會呈現。 第二個圖顯示「訪客」= {...}的子集的資料，其中「天」是以「日」維度中4月1日至4月5日的元素選取為基礎。

![](assets/client-sub1.png)
