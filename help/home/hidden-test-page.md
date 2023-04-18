---
title: 隱藏的測試頁
description: 此頁面會在搜尋和目錄中隱藏
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
source-git-commit: 73c7ad435917ab17022494f6f73d2c626363dcc2
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 2%

---

# 隱藏的測試頁

## 徽章

徽章是用作內容指示器的彩色標籤。 例如，您可以新增徽章，將文章標示為 _Beta_ 或區段作為 _Premium_. 您可以變更徽章的顏色，並關聯URL和工具提示。

[!BADGE 徽章範例]

徽章有兩種類型，每種語法不同：

* **中繼資料**  — 在頁面頂端附近顯示徽章
* **內嵌**  — 顯示語法所在的徽章

### 中繼資料徽章

在中繼資料中新增徽章語法時，會在文章的頁面標題(H1)上方放置徽章。

您可以為徽章命名，例如，使用 _徽章1_ 或 _徽章2_. 或者，您可以更有創意(只要名稱開頭為 _徽章_)。

中繼資料範例：

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium:** 此範例顯示Premium徽章，內含URL和工具提示。

* **badgeExam:** 此示例顯示帶有考試ID號的深色徽章。

#### 內嵌徽章

在標題、表格或其他頁面元素中，指定標章資訊。

以下是內嵌徽章的語法，其中包含測試版標籤、藍色、URL和工具提示：

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### 可用徽章顏色

徽章使用「Adobe光譜」中定義的顏色：

| 類型 | 徽章 |
|---|---|
| 資訊（預設） | [!BADGE Beta]{type=Informative url="https://www.example.com"} |
| 正面 | [!BADGE 新功能]{type=Positive url="https://www.example.com" tooltip="前往example.com"} |
| 負面 | [!BADGE 已終止]{type=negative tooltip="此功能現已終止"} |
| 中性 | [!BADGE 也許]{type=Neutral tooltip="一個騎手從馬上摔下來……"} |
| 注意 | [!BADGE 注意]{type=Caution tooltip="黃色狀態"} |

語法範例

```
|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off the horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|
```

### 徽章要求

* 中繼資料中僅允許兩個徽章。 此規則可設定，因此若您需要例外，請通知我們。
* 僅需要徽章標籤。 此 `type`, `url`，和 `tooltip` 參數為選用。 此 `type` 參數決定顏色。 此 `url` 參數可讓使用者按一下徽章以開啟文章或頁面。 此 `tooltip` 參數會在滑鼠上顯示工具提示文字。
* 新增徽章至 `TOC.md` 檔案會顯示指南中每篇文章的徽章。 如果您指定徽章的URL以跳至文章，請確定您使用根連結(例如 `/help/guide/article.md`)而非相對連結(例如 `article.md`)來說明不同資料夾中的文章。
* 新增徽章至 `metadata-new.md` 在存放庫中的每篇文章上顯示徽章。
* 對於中繼資料徽章，請確定所有值都以引號括住。 針對內嵌徽章，請確定 `url` 和 `tooltip` 會以引號括住。
* 有效類型值包括 *資訊* （預設，藍色）, *正* （綠色）, *負數* （紅色）, *中性* （深灰色），和 *注意* （黃色）。
* 徽章標籤已本地化。
* 如果指定了多個中繼資料徽章，則會根據徽章名稱，以字母順序顯示徽章，例如 `badge1:` 或 `badgeWeb`.
* 如果您想要在新索引標籤中開啟URL，請使用下列語法：

   ```
   [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
   ```

   已呈現:

   [!BADGE 在新索引標籤中開啟]{type=Negative url="https://www.adobe.com newtab=true" tooltip="在新索引標籤中開啟adobe.com"}

## 文字醒目提示

Workfront團隊要求能使用黃色醒目提示來指出即將推出功能的預覽。 這是它的運作方式。

範例 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

已呈現:

不應強調這一整段。 <span class="preview"> 這個詞是 **粗體** 在一句突出的句子裡。</span> 這只是最後一句。

範例 2:

```
Highlighting should start after this paragraph.

<div class="preview">

**This is a test**

>[!TIP]
>
>Drink 6 cups of water a day.

Last highlighted paragraph

</div>

Not highlighted
```

已呈現：在本段之後應開始強調。

<div class="preview">

**這是個測試**

>[!TIP]
>
>每天喝6杯水。

最後強調的段落

</div>

未突出顯示

一般規則是使用 `<span class="preview">` 突出顯示段落中的段落或文本，並使用 `<div class="preview">` 適用於多個段落和元件。

## 程式碼區塊的語法醒目提示

Experience League支援程式碼區塊的語法醒目提示。 請務必指定語言，例如 `java` 在開啟的反引號集之後，確定語法已正確反白顯示。 如需有效語言的清單，請參閱 [https://prismjs.com](https://prismjs.com/#supported-languages). 如果缺少任何語言，請記錄日誌票證。

### 代碼塊中的行編號

新增 `{line-numbers="true"}` 在語言之後啟用行編號。

行號(&grave;&grave;&grave;&grave;;`html {line-numbers="true"}`):

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**開始第_行編號**

新增 `start-number="n"` 在行號語法之後，以開始對1以外的數字進行編號。

新起始行(&grave;&grave;&grave;&grave;)的示例；`html {line-numbers="true" start-line="7"}`):

```html {line-numbers="true" start-line="7"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```

### 程式碼區塊中的線條醒目提示

新增 `highlight="n"` 在行號語法之後，反白標示程式碼區塊中的列。 指定 `11-13, 16` 將突出顯示11 - 13和16行。

行突出顯示的示例(&grave;&grave;&grave;&grave;;`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`):

```html {line-numbers="true" start-line="7" highlight="11-13, 16"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```
