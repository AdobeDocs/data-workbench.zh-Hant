---
description: Data Workbench現在支援輸入法編輯器(IME)，作為國際語言的次要文字輸入程式。
title: 安裝輸入法編輯器
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56,0bdc7d95-b49a-4ca5-9fde-9c1ce2cd14ec,e4e1c016-0544-434a-b82e-fdd2a4af316c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# 安裝輸入法編輯器{#installing-the-input-method-editor}

Data Workbench現在支援輸入法編輯器(IME)，作為國際語言的次要文字輸入程式。

IME允許您使用各種適合本地語言的方法輸入國際字元。 Data Workbench提供輸入對話方塊，可讓您開啟並使用所需的IME來處理文字欄位。

>[!NOTE]
>
>Data Workbench 6.1版僅支援虛擬簡體中文鍵盤。 通過輸入輸入其他語言可能會導致意外行為。

## 使用IME {#section-5f008d75a7b24119ab6aebc55454f927}

要使用浮動IME文本輸入功能，請執行以下操作：

1. 按一下&#x200B;**[!UICONTROL Alt + Space]**&#x200B;以查看任何文本輸入區域。
1. 使用系統的IME輸入值。
1. 選擇&#x200B;**[!UICONTROL Enter]**&#x200B;鍵或按一下&#x200B;**[!UICONTROL OK]**&#x200B;按鈕，關閉輸入對話框。

   對話框將消失，然後字元將出現在選定欄位中。

**更新Insight.cfg檔案**

要採用IME，必須使用此設定更新[!DNL Insight.cfg]檔案：

```
Localized IME = bool: true
```

如果配置檔案中不存在此設定，則按&#x200B;**[!UICONTROL Alt + Space]**&#x200B;將不參與IME功能。

**以其他語言啟動Insight:** 為了更能支援本地化資產（例如開始畫面），以及日後支援多種語言，Data Workbench需要命令列引數來識別要載入的語言。預設語言是英文。

若要啟動中文的Data Workbench，您必須使用「 — zh-cn」引數叫用[!DNL Insight.exe]:

```
Insight.exe -zh-cn
```

（這些命令行參數不區分大小寫。）
