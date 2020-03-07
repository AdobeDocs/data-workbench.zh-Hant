---
description: 資料工作台現在支援輸入法編輯器(IME)，做為國際語言的次要文字輸入程式。
solution: Analytics
title: 安裝輸入法編輯器
topic: Data workbench
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安裝輸入法編輯器{#installing-the-input-method-editor}

資料工作台現在支援輸入法編輯器(IME)，做為國際語言的次要文字輸入程式。

IME可讓您使用多種適合您當地語言的方法輸入國際字元。 資料工作台提供輸入對話方塊，可讓您開啟並使用所要的文字欄位IME。

>[!NOTE]
>
>在資料工作台6.1版本中，僅支援虛擬簡體中文鍵盤。 通過IME輸入其他語言可能會導致意外行為。

## 使用IME {#section-5f008d75a7b24119ab6aebc55454f927}

要使用浮動IME文本輸入功能：

1. 按一 **[!UICONTROL Alt + Space]** 下以取得任何文字輸入區域。
1. 使用系統的IME輸入值。
1. 選擇鍵或按一下按鈕， **[!UICONTROL Enter]** 關閉輸入對 **[!UICONTROL OK]** 話框。

   對話框將消失，字元將出現在選定欄位中。

**更新Insight.cfg檔案**

若要採用IME，您必須使用下列設 [!DNL Insight.cfg] 定更新檔案：

```
Localized IME = bool: true
```

如果配置檔案中不存在此設定，則按鍵 **[!UICONTROL Alt + Space]** 將不與IME功能交互。

**以其他語言啟動Insight:** 為了更好地支援本地化資產（例如啟動顯示畫面），以及未來支援多種語言，資料工作台需要使用命令列引數來識別要載入的語言。 預設語言為英文。

啟動中文資料工作台時， [!DNL Insight.exe] 您必須使用&quot;-zh-cn&quot;引數叫用：

```
Insight.exe -zh-cn
```

（這些命令行參數不區分大小寫。）
