---
description: 本節說明不同類型的Dimension，以及如何在DWB中設定。
title: 維度設定
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
exl-id: 04afd773-e938-49f7-83c9-1d706a6dc525
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 4%

---

# 維度設定{#dimension-setup}

{{eol}}

本節說明不同類型的Dimension，以及如何在DWB中設定。

## 什麼是Dimension {#section-dac631943df24706827cedc6f0641543}

在最基本的層級，維度是可劃分資料集中資料的類別。

最佳實務：資料結構中的Dimension可以提供任何名稱。 本課程中使用和說明的Dimension名稱被視為最佳實務。 Dimension的名稱可能不同。 當您接觸到其他資料集時，就會開始看到資料集的差異。 請務必了解維度的用途，而非其名稱。 例如，無論名稱是「訪客」、「客戶」、「人員」、「消費者」或「使用者」，請務必了解這些辭彙通常用來指稱用於收集單一人員相關資訊的最高層級可數維度。

如需完整資訊，請參閱 [資料集組態](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-dataset-constr.html) 指南。

## DWB中的Dimension類型 {#section-a4fbb7bf2bde44528ac0f94a96465862}

Data Workbench中有兩種維度類型：延伸Dimension和衍生Dimension。

擴充Dimension是從「原始」資料檔案中的欄位建立。 擴充維度可用來分類「原始」資料，並指定資料之間的關係。 延伸維度是由Data Workbench架構師建立。

衍生Dimension是使用現有的延伸維度定義處理資料集後，由使用者「在用戶端」建立。 例如，根據現有的URI維，用戶可以選擇建立派生的「頁面名稱」維，該維將顯示更易記的頁面名稱，取代指定的URI。 所有維度都包含已分類（分組）以形成維度的元素或項目。 以下是三個維度及其元素。

有許多衍生維度都是自動建立的，用以執行不同類型的視覺化。例如，當使用者建立網站或程式圖時，DWB伺服器會建立「首碼」維度。 其他像是報告時間維度，則是由設定檔的「維度」目錄中的檔案所定義。

>[!NOTE]
>
>任何指定維度中顯示的元素，只會反映記錄中存在且選擇載入資料集的值。 例如，如果沒有「12年5月」的資料，則該月不會顯示在「月」維度中。

## 延伸維度 {#section-5fc51fa539034941a30a2df606f7d727}

延伸維度類型

**1)可數Dimension**

最高層級是可數維度。 可數維度提供兩個主要函式。 首先，這些維度是您想要計算的元素。 換句話說，可數可回答以下問題：

* 「有多少訪客瀏覽了您的首頁？」
* 「來自google.com的瀏覽數？」

因此，可數通常作為建立量度的基本基本建置區塊。

可數的第二項主要功能是，它們構成資料集結構的骨幹。 您的資料結構和所有其他維度會組織成分組在下，並屬於可數。 換句話說，如果將維度視為「類別」，則可數是將這些「類別」組織成群組的方式。

將維度分組在可數維度下時，會說明維度位於可數維度的「層級」。 例如，「電子郵件地址」可以在訪客層級，而「瀏覽器」則可以在瀏覽層級。 「父項」和「子項」是指可數與其下分組的維度之間的關係。 例如，訪客是電子郵件地址的「父項」。 相反地，電子郵件地址是訪客的「子項」。

**2)簡單Dimension**

所有維中最常見的是「簡單」維。 簡單維度與父項可數維度間具有一對多關係，通常用於視覺效果中，以便您檢視其元素。 這表示可數維度可以對簡單維度有一個值，但簡單維度可以屬於一或多個可數。 例如，客戶的名稱為「John」，該客戶只能有一個名字，但是，其他許多客戶的名稱為「John；」。 作為另一個範例，只能將一個瀏覽器（例如Firefox）用於任何特定網站造訪，但該瀏覽器可用於許多不同的造訪。

如果可數維度回答「多少？」，則簡單維度會回答「哪些？」。 使用上述可數維度區段中使用的相同範例；頁面名稱是簡單維度。 使用表格和簡單維度「頁面名稱」，我們可以回答下列問題：

* 「哪個頁面的頁面檢視次數最多？」
* 「在所有購物車頁面中，哪個頁面的瀏覽次數最多？」

**3)多對多Dimension**

與父項可數維度間有多對多關係。 例如，如果名為「外部搜尋詞」的維度位於「造訪」層級；指定的外部搜尋詞可用於一或多次瀏覽，而指定的瀏覽可包含一或多個外部搜尋詞。 因此，外部搜尋詞是多對多維度。

**4)數值Dimension**

數值維度是具有數值的簡單維度類型。 數值維度的建立通常用於量度。 數值維度的範例包括「收入」、「訂購」和「件數」。 在上述範例中，「客戶訂單」是數值維度。
**5)非正規Dimension** 非正規維度是與父項可計數維度具有一對一關係的維度。 非正規維度通常與身分識別資料等基數較高（許多不重複元素）的維度搭配使用。 例如，訪客只能有一個使用者ID，而使用者ID只能屬於一個訪客。 因此，這是一對一關係，可以是非正規維度。

例如，「Geometrixx網頁使用者ID」是客戶層級的非正規維度。 由於為非正規行為，因此與其父維度間具有一對一關係，這表示每個Web使用者ID都有一個客戶，而每個客戶只有一個Web使用者ID。 因此，「Geometrixx」量度對於Web使用者ID的每個元素只能是「1」。

**6)時間Dimension**

時間維度可讓您根據指定的時間戳記欄位，建立一組定期或絕對的當地時間維度。 時間維度的範例包括「日」、「小時」、「周」和「小時」。 在上述範例中，「小時」表格顯示在一天中不同的小時內，接收了多少次瀏覽和頁面檢視。

>[!NOTE]
>
>用於顯示格式的%逸出與標準C庫相同 *strftime*.

## 定義延伸維度 {#section-38ee124ec74b43fb95f13194a9582b97}

定義延伸Dimension的步驟：

1. 使用資料集設定檔時，請開啟「設定檔管理員」 ，然後按一下「資料集」以顯示其內容。
1. 開啟Transformation.cfg檔案或要在其中定義擴展維的Transformation Dataset Include檔案。
1. 按一下右鍵「轉換」 ，然後按一下「新增」 > `<Extended dimension type>`.
1. 輸入延伸維度的適當資訊。 有關轉換類型的說明及其參數的資訊，請參閱以下各節：

   * [可數維度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [簡單維度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [多對多維度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [數值維度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [非正規維度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [時間維度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. 對於您定義的任何擴展維，可以在「注釋」參數中添加一個或多個注釋行，以進一步說明該維或添加有關其使用的注釋。 若要新增註解，請以滑鼠右鍵按一下 *註解* 標籤，然後按一下*「新增>注釋行」*。

1. 在設定檔案中定義延伸維度後，請將檔案儲存在本機，然後儲存至DWB伺服器上的資料集設定檔。

## 隱藏延伸維度 {#section-02339fb51658418eabc10186cd5957d7}

可隱藏延伸Dimension，以免顯示在DWB的「Dimension功能表」中。 要隱藏維，請在維定義中將「隱藏」屬性設定為「True」。
