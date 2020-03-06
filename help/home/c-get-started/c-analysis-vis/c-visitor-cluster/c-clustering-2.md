---
description: Cluster Builder現在包含KMeans++演算法（之前僅支援KMeans演算法），可使用更快的方式來尋找加速叢集產生程式的中心。
title: Clustering 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Clustering 2.0{#clustering}

Cluster Builder現在包含KMeans++演算法（之前僅支援KMeans演算法），可使用更快的方式來尋找加速叢集產生程式的中心。

## KMeans演算法 {#section-92383a1be1d6402c95a25c902e90b850}

在「叢集產 [生器」中](https://docs.adobe.com/help/en/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html)，您現在可以選取 **[!UICONTROL Options]** >，以 **[!UICONTROL Algorithm]** 在定義叢集時選取演算法。

* **[!UICONTROL KMeans]**。該算法利用樹冠聚類來定義樹冠的中心。
* **[!UICONTROL KMeans++]**。該算法在對大量資料集運行時加快了集群構建。

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++是KMeans聚類算法的一種改進實現方式，它提供了較好的初始k中心初始化。 （原始KMeans算法隨機選擇初始中心。）KMeans++隨機選擇第一個中心。 剩餘的k-1中心將根據資料點與最近現有中心之間的距離逐個選擇。 與附近的資料點相比，最遠的資料點更有可能被選擇為新的中心。 選擇初始中心後，該過程與原始KMeans聚類完全相同。

KMeans++的工作流程與KMeans叢集的工作流程完全相同，但您必須在叢集產生器中選取 **Options** > **Algorithm** > **KMeans++** 。

>[!NOTE]
>
>每個DPU在其自己的資料部分上運行其自己的KMeans++過程。 如果DPU有足夠的可用記憶體（此比率可在PAServer.cfg檔案中配置），則這些相關變數的資料將帶入記憶體。 剩餘的k-1初始中心選擇和收斂迭代都發生在記憶體中，比以前的KMeans聚類快。

