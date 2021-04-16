---
description: 資料工作台現在支援輸入法編輯器(IME)，做為國際語言的次要文字輸入程式。
title: 安裝輸入法編輯器
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56,0bdc7d95-b49a-4ca5-9fde-9c1ce2cd14ec,e4e1c016-0544-434a-b82e-fdd2a4af316c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# 安裝輸入法編輯器{#installing-the-input-method-editor}

資料工作台現在支援輸入法編輯器(IME)，做為國際語言的次要文字輸入程式。

IME可讓您使用多種適合您當地語言的方法輸入國際字元。 資料工作台提供輸入對話方塊，可讓您開啟並使用所要的文字欄位IME。

>[!NOTE]
>
>在資料工作台6.1版本中，僅支援虛擬簡體中文鍵盤。 通過IME輸入其他語言可能會導致意外行為。

## 使用IME {#section-5f008d75a7b24119ab6aebc55454f927}

要使用浮動IME文本輸入功能：

1. 按一下&#x200B;**[!UICONTROL Alt + Space]**&#x200B;以查看任何文本輸入區域。
1. 使用系統的IME輸入值。
1. 選擇&#x200B;**[!UICONTROL Enter]**&#x200B;鍵或按一下&#x200B;**[!UICONTROL OK]**&#x200B;按鈕，關閉輸入對話框。

   對話框將消失，字元將出現在選定欄位中。

**更新Insight.cfg檔案**

要使用IME，您必須使用以下設定更新[!DNL Insight.cfg]檔案：

```
Localized IME = bool: true
```

如果配置檔案中不存在此設定，則按&#x200B;**[!UICONTROL Alt + Space]**&#x200B;鍵將不參與IME功能。

**以其他語言啟動Insight:** 若要更佳地支援本地化資產（例如啟動顯示畫面），並在未來支援多種語言，資料工作台需要使用命令列引數來識別要載入的語言。預設語言為英文。

啟動中文資料工作台時，您必須使用&quot;-zh-cn&quot;引數叫用[!DNL Insight.exe]:

```
Insight.exe -zh-cn
```

（這些命令行參數不區分大小寫。）
