---
description: 本節說明不同類型的「尺寸」以及如何在DWB中設定它們。
title: 維設定
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# 維設定{#dimension-setup}

本節說明不同類型的「尺寸」以及如何在DWB中設定它們。

## 什麼是維度 {#section-dac631943df24706827cedc6f0641543}

在最基本的層級，維度是資料集中資料可劃分的類別。

最佳實務：可以提供資料架構中的維的任何名稱。 本課程中使用和解釋的維度名稱被視為最佳實務。 維度的命名方式可不同。 當您接觸到其他資料集時，就會開始看到資料集的差異。 請務必瞭解維度的目的，而非其名稱。 例如，不論是稱為「訪客」、「客戶」、「人員」、「消費者」或「使用者」，請務必瞭解這些術語通常用來指用於收集單一人員資訊的最高層可計數維度。

如需完整資訊，請參 [閱資料集設定指南](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html) 。

## DWB中的維類型 {#section-a4fbb7bf2bde44528ac0f94a96465862}

「資料工作台」中有兩種維度類型：擴展尺寸和派生尺寸。

「延伸維度」是從「原始」資料檔案的欄位建立。 延伸維度可用來分類「原始」資料，並指定資料之間的關係。 延伸維度由資料工作台架構師建立。

在使用現有的延伸維度定義處理資料集後，衍生維度是由使用者「在用戶端」建立。 例如，根據現有的URI維度，使用者可選擇建立衍生的頁面名稱維度，以顯示更易用的頁面名稱來取代指定的URI。 所有維都由元素或項目組成，這些元素或項目已分類（分組）在一起以形成維。 以下是三個維度及其元素。

有許多衍生維度都是自動建立的，用以執行不同類型的視覺化。例如，當使用者建立網站或程式地圖時，DWB伺服器會建立「首碼」維度。 其他像是報告時間維度，則是由設定檔的「維度」目錄中的檔案所定義。

>[!NOTE]
>
>出現在任何指定維度中的元素只會反映選擇載入資料集的記錄中的值。 例如，如果沒有「5月12日」的資料，則該月份不會出現在「月」維度中。

## Extended Dimensions {#section-5fc51fa539034941a30a2df606f7d727}

擴展尺寸類型

**1)可計數維度**

最高層是可計數的維度。 可計數的維度提供兩個主要功能。 首先，它們是您要計算其元素的維度。 換言之，可計數器可回答以下問題：

* 「有多少訪客瀏覽了您的首頁？」
* 「有多少次瀏覽來自google.com?」

因此，計數通常被用作建立量度的基本基本建置區塊。

可計數表的第二個主要功能是它們構成了資料集模式結構的骨幹。 您的資料結構和所有其他維度會組織成群組在下方，且屬於可計數的。 換言之，如果我們將維度視為「類別」，則可計數是我們將這些「類別」組織成群組的方式。

當維度分組在可計數維度下時，這些維度據說位於可計數維度的「層級」。 例如，「電子郵件地址」可位於訪客層級，「瀏覽器」位於瀏覽層級。 「父項」和「子項」是指可計數與其下方分組的維度之間的關係。 例如，訪客是電子郵件地址的「父」。 相反地，電子郵件地址是訪客的「子系」。

**2)簡單尺寸**

所有尺寸中最常見的是「簡單」尺寸。 簡單維度與父項可計數維度有一對多關係，通常用於視覺化中，因此您可以檢視其元素。 這表示可計數維度對於簡單維度可以有一個值，但簡單維度可屬於一或多個可計數。 例如，客戶的名稱為「John」-該客戶只能有一個名字，但是，許多其他客戶可以有名字「John;」。 另一個範例是，只有一個瀏覽器（例如Firefox）可用於任何特定的網站瀏覽，但該瀏覽器可用於許多不同的瀏覽。

如果可計數維度回答「多少？」，則簡單維度回答「哪些？」。 使用上述可計數維度區段中的相同範例；頁面名稱是簡單維度。 使用表格和簡單維度「頁面名稱」，我們可以回答以下問題：

* 「哪個頁面檢視次數最多？」
* 「在所有購物車頁面中，哪個頁面瀏覽次數最多？」。

**3)多對多維度**

多對多維度與父項可計數維度有多對多關係。 例如，如果名為「外部搜尋詞」的維度位於「瀏覽」層級；指定的外部搜尋詞可用於一或多個瀏覽，而指定的瀏覽可能包含一或多個外部搜尋詞。 因此，外部搜尋詞是多對多維度。

**4)數值維度**

數值維度是具有數值的簡單維度類型。 數值維度通常建立為用於度量。 數值維度的範例包括「收入」、「訂購」和「件數」。 在上述範例中，「客戶訂單」是數值維度。
**5)非正規維度** 非正規維度是指與父項可計數維度有一對一關係的維度。 非正規維度通常與具有高基數（許多唯一元素）的維度（例如識別資料）搭配使用。 例如，訪客只能有一個使用者ID，而使用者ID只能屬於一位訪客。 因此，這是一對一關係，可以是非正規維度。

例如，Geometrixx Web使用者ID是客戶層級的非正規維度。 由於非正規，因此與其父項維度有一對一的關係，這表示每個Web使用者ID有一個客戶，而每個客戶只有一個Web使用者ID。 因此，Geometrixx Web使用者ID的每個元素的「客戶」量度只能是「1」。

**6)時間維度**

時間維度可讓您根據您指定的時間戳記欄位，建立一組定期或絕對的本機時間維度。 時間維度的範例包括「日」、「小時」、「周」和「一天中的小時」。 在上述範例中，「一天中的某小時」表格顯示在一天中不同小時收到的瀏覽和頁面檢視次數。

>[!NOTE]
>
>用於顯示格式的%轉義與標準C庫strftime *相同*。

## 定義擴展尺寸 {#section-38ee124ec74b43fb95f13194a9582b97}

定義擴展維的步驟：

1. 在資料集描述檔中工作時，開啟「描述檔管理員」並按一下「資料集」以顯示其內容。
1. 開啟Transformation.cfg檔案或您要定義擴充維度的Transformation Dataset Include檔案。
1. 按一下右鍵「轉換」，然後按一下「添加新」> `<Extended dimension type>`。
1. 為延伸維度輸入適當的資訊。 有關轉換類型的說明及其參數的資訊，請參見以下各節：

   * [可計數的維度](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [簡單尺寸](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [多對多維度](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [數值維度](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [非正規維度](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [時間維度](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. 對於您定義的任何擴展維，可以在「注釋」參數中添加一個或多個注釋行，以進一步描述該維或添加有關其使用的注釋。 若要新增註解，請以滑鼠右鍵按一下「注 *解」標籤* ，然後按一下*「新增>註解行」。

1. 在設定檔案中定義擴充維度後，將檔案儲存在本機，並儲存到DWB伺服器上的資料集描述檔。

## 隱藏延伸維度 {#section-02339fb51658418eabc10186cd5957d7}

「延伸尺寸」(Extended Dimensions)可隱藏，因此不會顯示在DWB的「尺寸」(Dimension)選單中。 要隱藏維，請在維定義中將「隱藏」屬性設定為「True」。
