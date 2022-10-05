---
description: Data Workbench現在支援輸入法編輯器(IME)，作為國際語言的次要文字輸入程式。
title: 安裝輸入法編輯器
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# 安裝輸入法編輯器{#installing-the-input-method-editor}

{{eol}}

Data Workbench現在支援輸入法編輯器(IME)，作為國際語言的次要文字輸入程式。

IME允許您使用各種適合本地語言的方法輸入國際字元。 Data Workbench提供輸入對話方塊，可讓您開啟並使用所需的IME來處理文字欄位。

>[!NOTE]
>
>Data Workbench 6.1版僅支援虛擬簡體中文鍵盤。 通過輸入輸入其他語言可能會導致意外行為。

## 使用輸入法 {#section-5f008d75a7b24119ab6aebc55454f927}

要使用浮動IME文本輸入功能，請執行以下操作：

1. 按一下 **[!UICONTROL Alt + Space]** 的URL。
1. 使用系統的IME輸入值。
1. 選取 **[!UICONTROL Enter]** 鍵或按一下 **[!UICONTROL OK]** 按鈕。

   對話框將消失，然後字元將出現在選定欄位中。

**更新Insight.cfg檔案**

要採用IME，您必須更新 [!DNL Insight.cfg] 檔案（具有此設定）:

```
Localized IME = bool: true
```

如果配置檔案中不存在此設定，請按 **[!UICONTROL Alt + Space]** 不會與IME功能相接觸。

**以其他語言啟動Insight:** 為了更能支援啟動畫面等本地化資產，以及日後支援多種語言，Data Workbench需要命令列引數，用以識別要載入的語言。 預設語言是英文。

若要啟動中文版Data Workbench，您必須叫用 [!DNL Insight.exe] 帶有「 — zh-cn」參數：

```
Insight.exe -zh-cn
```

（這些命令行參數不區分大小寫。）
