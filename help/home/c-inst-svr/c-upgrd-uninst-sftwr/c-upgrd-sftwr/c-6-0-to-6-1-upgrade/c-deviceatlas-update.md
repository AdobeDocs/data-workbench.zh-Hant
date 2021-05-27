---
description: DeviceAtlas JSON檔案現在將以.bundle檔案（重新命名為.tar.gz）及DeviceAtlas.dll和DeviceAtlas64.dll檔案分發。
title: DeviceAtlas 分發
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
exl-id: e9671810-d32c-4ec4-a1cb-54b71c6f101c,333507bb-3e8b-4da1-8218-b35fcf8d5f80,aa811c7b-ef80-4f23-b395-0cbb7d2677a9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# DeviceAtlas 分發{#deviceatlas-distribution}

DeviceAtlas JSON檔案現在將以.bundle檔案（重新命名為.tar.gz）及DeviceAtlas.dll和DeviceAtlas64.dll檔案分發。

當管理員將Insight Server升級至6.0版時，DeviceAtlas.bundle檔案會隨升級套件一併包含於以下位置的軟體和檔案設定檔（軟體檔案設定檔）中：

[!DNL Server Packages > v6.00 > Server_6.00.zip]

將DeviceAtlas.bundle檔案提取到[!DNL Server\Lookups\DeviceAtlas]。

DeviceAtlas.bundle檔案應放置在與DPU同步的目錄中，而與新DeviceAtlasComponent對應的DeviceAtlas.cfg檔案應放置在同步主版的「處理伺服器的元件」目錄中。 變更DeviceAtlas.bundle檔案時，下一個DeviceAtlas查閱呼叫將會根據更新的API和/或JSON檔案取得結果。

## 修改Transformation.cfg檔案{#section-394823348f5740028666e62e2bd42754}

DeviceAtlas轉換不再需要指定JSON檔案的路徑。 轉換.cfg檔案中定義的任何舊版DeviceAtlasTransformation，都不應再包含指向模糊化JSON檔案的File參數。

此範例Transformation.cfg檔案顯示應刪除的File引數，以避免混淆。 （將其留在那裡不會造成傷害，但只會造成潛在的混淆，因為它會被忽略。）

```
6 = DeviceAtlasTransformation:  
  Comments = Comment: 0 items  
  Condition = AndCondition: 0 items

<b></b> 
<filepath>
  File = string: Lookups\\DeviceAtlas\\20110106_private.json.obfuscated 
</filepath> 
  ^^ DELETE THE ABOVE LINE FROM ALL PREVIOUS TRANSFORMATIONS ^^  
 
  Name = string: DeviceAtlas Lookup  
  Outputs = vector: 4 items  
    0 = Column:  
      Column Name = string: vendor  
      Field Name = string: x-vendor  
    1 = Column:  
      Column Name = string: model  
      Field Name = string: x-model  
    2 = Column:  
      Column Name = string: isBrowser  
      Field Name = string: x-isbrowser  
    3 = Column:  
      Column Name = string:usableDisplayHeight  
      Field Name = string: x-usable-display-height 
User Agent = string: x-ua  
```

## 修改DeviceAtlas.cfg檔案{#section-10b43705a6c846fd9ec54ea6be249f88}

這是DeviceAtlas.cfg檔案中所需的[!DNL component]引數的範例。

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

從「配置檔案同步」功能的角度看，此DeviceAtlas.bundle檔案將被視為配置檔案。 此外，JSON資料和DLL將用於元件級別，而非單個轉換級別。

新的DeviceAtlasComponent在啟動時會找到.bundle聚合，將JSON檔案去模糊化到記憶體中，將檔案提取到臨時目錄中，並為運行平台載入相應的DLL。 此元件還監視對捆綁檔案的更改，並在更改時自動重新載入DLL和.cfg檔案。

## 運行DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

正確的設定會在轉換所需的時間上產生很大差異。 轉換可設定為每個工作階段每位訪客只執行一次，以便DeviceAtlas加速處理程式。

**如果使用Log Processing.cfg部署**:

執行兩次轉換。

1. 只查找[!DNL mobile id]欄位，然後
1. 建立條件以忽略[!DNL mobile id]，然後查找其餘欄位。

**如果使用Transformation.cfg部署**:

如上述「記錄處理」的步驟1部署，或使用跨列支援條件式設定。

* 交叉行(Cross-Rows) — 抓取上一個會話鍵。 然後識別目前的工作階段金鑰是否與使用跨列找到的工作階段金鑰不同。 如果是，則DeviceAtlas轉換將只在每個工作階段的一個記錄上執行。
