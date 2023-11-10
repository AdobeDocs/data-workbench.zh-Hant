---
title: 隱藏測試頁面
description: 此頁面在搜尋和目錄中隱藏
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="下載Premium"
badgeExam: label="考試ADO-E903" type="neutral"
exl-id: 02245655-511e-4e89-8846-dac85681ea91
source-git-commit: 6a10bc9a2ed41223070f3eba94b8ea7b4b1b77ab
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 4%

---

# 隱藏測試頁面

啟動? 下午3:10左右重新檢查提交。 將會在下午3:30上線嗎？

## 預覽問題

下列段落無法在VSC預覽中正確呈現。 我不確定為什麼。

如果您的密碼是由 [!DNL Adobe]，您可以 [變更您Adobe帳戶中的密碼](https://helpx.adobe.com/manage-account/using/change-or-reset-password.html){target="_blank"}.

## 附註型別

所有支援的註記型別。

>[!NOTE]
>
>This is a standard NOTE block.

>[!TIP]
>
>This is a standard tip.

>[!IMPORTANT]
>
>這是重要注意事項。

>[!WARNING]
>
>這是警告。

>[!CAUTION]
>
>這是警告。

>[!ADMIN]
>
>這是呈現為「管理」的管理員備註。 僅限EXL。

>[!AVAILABILITY]
>
>這是可用性注意事項。 僅限EXL。

>[!PREREQUISITES]
>
>這是先決條件注意事項。 僅限EXL。

>[!INFO]
>
>這是資訊備註。 僅限EXL。

>[!ERROR]
>
>這是錯誤備註。 僅限EXL。

>[!SUCCESS]
>
>這是Success附註。 僅限EXL。

>[!MORELIKETHIS]
>
>* 頁面 1
>* 頁面 2

## 徽章

徽章是用作內容指示器的彩色標籤。 例如，您可以新增徽章，將文章標示為 _測試版_ 或區段為 _Premium_. 您可以變更徽章的顏色，並建立URL與工具提示的關聯。

[!BADGE 徽章範例]

有兩種型別 of 徽章，每個都具有不同的語法：

* **中繼資料**  — 在頁面頂端附近顯示徽章
* **內嵌**  — 顯示語法所在的徽章

### 中繼資料徽章

在中繼資料中新增徽章語法可將徽章放置在文章的頁面標題(H1)上方。

例如，您可以使用以下名稱來命名徽章： _徽章1_ 或 _徽章2_. 或者，您可以更有創意(只要名稱開頭為 _徽章_)。

中繼資料範例：

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium：** 此範例顯示帶有URL和工具提示的Premium徽章。

* **徽章考試：** 此範例顯示帶有考試ID號碼的深色徽章。

#### 內嵌徽章

在其自身行或標題、表格或其他頁面元素中指定徽章資訊。

以下是具有Beta版標籤、藍色顏色、URL和工具提示的內嵌徽章的語法：

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### 可用的徽章顏色

徽章使用Adobe光譜中定義的顏色：

| 類型 | 徽章 |
|---|---|
| 資訊（預設） | [!BADGE Beta]{type=Informative url="https://www.example.com"} |
| 正面 | [!BADGE 新功能]{type=Positive url="https://www.example.com" tooltip="前往example.com"} |
| 負面 | [!BADGE 已終止]{type=negative tooltip="此功能現已終止服務"} |
| 中性 | [!BADGE 可能]{type=Neutral tooltip="一名騎手從馬上掉了下來……"} |
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

### 徽章的需求

* 中繼資料中只允許兩個徽章。 此規則可設定，因此如果您需要例外狀況，請通知我們。
* 只需要徽章標籤。 此 `type`， `url`、和 `tooltip` 引數為選用專案。 此 `type` 引數會決定顏色。 此 `url` 引數可讓使用者按一下徽章，以開啟文章或頁面。 此 `tooltip` 引數會顯示滑鼠懸停時的工具提示文字。
* 新增徽章至 `TOC.md` 檔案會顯示指南中每篇文章的徽章。 如果您指定讓徽章跳至文章的URL，請務必使用根連結(例如 `/help/guide/article.md`)不是相對連結(例如， `article.md`)來說明不同資料夾中的文章。
* 新增徽章至 `metadata-new.md` 在存放庫中的每個文章上顯示徽章。
* 對於中繼資料徽章，請確定所有值都用引號包住。 對於內嵌徽章，請確定 `url` 和 `tooltip` 都會用引號包住。
* 有效的型別值包括 *資訊性* （預設，藍色）， *正面* （綠色）， *負面* （紅色）， *中性* （深灰色），和 *注意* （黃色）。
* 徽章標籤已本地化。
* 如果指定了多個中繼資料徽章，會根據徽章名稱以字母順序顯示徽章，例如 `badge1:` 或 `badgeWeb`.
* 如果您想要URL在新索引標籤中開啟，請使用以下語法：

  ```
  [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
  ```

  已呈現:

  [!BADGE 在新標籤中開啟]{type=Negative url="https://www.adobe.com newtab=true" tooltip="在新標籤中開啟adobe.com"}

## 文字反白顯示

Workfront團隊要求能夠使用黃色反白來指示即將推出的功能預覽。 以下是運作方式。

範例 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

已呈現:

此整個段落不應反白顯示。 <span class="preview"> 這個字是 **粗體** 在醒目提示的句子內。</span> 這是最後一句。

範例 2:

```
Highlighting should start after this paragraph.

<div class="preview">

Start of DIV.

This is a new paragraph, then an image

![image](/help/home/assets/analytics-icon-24.png)

Last highlighted item.

</div>

Not highlighted
```

已呈現:

醒目提示應在此段落之後開始。

<div class="preview">

DIV的開頭。

這是新的段落，然後是影像

![影像](/help/home/assets/analytics-icon-24.png)

最後一個反白專案。

</div>

未醒目提示

## 程式碼區塊的語法醒目提示

Experience League支援程式碼區塊的語法醒目提示。 請務必指定語言，例如 `java` 在開頭的一組反引號之後，確定語法已正確反白。 如需有效語言的清單，請參閱 [https://prismjs.com](https://prismjs.com/#supported-languages). 如果有任何語言遺失，請記錄jira票證。

### 程式碼區塊中的行編號

新增 `{line-numbers="true"}` 在語言之後以啟用行編號。

行號(&amp;grave；&amp;grave；&amp;grave；`html {line-numbers="true"}`)：

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**開始線上上編號_**

新增 `start-number="n"` 在行號語法之後，在非1的編號上開始編號。

以新的起始線(&amp;grave；&amp;grave；&amp;grave；`html {line-numbers="true" start-line="7"}`)：

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

新增 `highlight="n"` 在行號語法之後，用於反白顯示程式碼區塊中的列。 指定 `11-13, 16` 會醒目顯示第11到13和16行。

反白線條(&amp;grave；&amp;grave；&amp;grave；`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`)：

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
