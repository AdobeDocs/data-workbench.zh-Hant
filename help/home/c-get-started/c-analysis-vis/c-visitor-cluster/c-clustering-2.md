---
description: 叢集產生器現在包含KMeans++演算法（先前僅支援KMeans演算法），可使用更快的方法來尋找加速叢集產生程式的中心。
title: Clustering 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
exl-id: 6a779ddc-c8f1-4c55-9c17-1119fe1aa791
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Clustering 2.0{#clustering}

叢集產生器現在包含KMeans++演算法（先前僅支援KMeans演算法），可使用更快的方法來尋找加速叢集產生程式的中心。

## KMeans演算法 {#section-92383a1be1d6402c95a25c902e90b850}

在[叢集產生器](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html?lang=en)中，您現在可以選取&#x200B;**[!UICONTROL Options]** > **[!UICONTROL Algorithm]**&#x200B;以在定義叢集時選取演算法。

* **[!UICONTROL KMeans]**。該算法利用樹冠聚類來定義樹冠簇的中心。
* **[!UICONTROL KMeans++]**。當對大資料集運行時，此算法可加快群集構建。

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++是KMeans聚類算法的改進實現，因為它提供了更好的初始k中心初始化。 （原始KMean算法隨機選擇初始中心。） KMeans++隨機選擇第一個中心。 剩餘的k-1中心將根據資料點到最接近現有中心的距離逐個選擇。 最遠的資料點被選擇為新中心的機會比附近的資料點更好。 選擇初始中心後，該過程與原始KMeans聚類完全相同。

KMeans++的工作流與KMeans群集的工作流完全相同，只是您需要在群集生成器中選擇&#x200B;**選項** > **算法** > **KMeans++**。

>[!NOTE]
>
>每個DPU都會在其自己的資料部分上運行自己的KMeans++過程。 如果DPU有足夠的可用記憶體（該比率可在PAServer.cfg檔案中配置），則這些相關變數的資料將被帶入記憶體。 剩餘的k-1初始中心選擇和收斂迭代都發生在記憶體中，這比以前的KMeans群集快。
