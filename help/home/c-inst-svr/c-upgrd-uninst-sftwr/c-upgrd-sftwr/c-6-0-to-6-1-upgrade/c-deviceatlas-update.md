---
description: DeviceAtlas JSON檔案現在會與DeviceAtlas.dll和DeviceAtlas64.dll檔案一起，以。bundle檔案（重新命名為。tar.gz）發佈。
title: DeviceAtlas 分發
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
exl-id: e9671810-d32c-4ec4-a1cb-54b71c6f101c,333507bb-3e8b-4da1-8218-b35fcf8d5f80,aa811c7b-ef80-4f23-b395-0cbb7d2677a9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# DeviceAtlas 分發{#deviceatlas-distribution}

DeviceAtlas JSON檔案現在會與DeviceAtlas.dll和DeviceAtlas64.dll檔案一起，以。bundle檔案（重新命名為。tar.gz）發佈。

當管理員將Insight Server升級至6.0版時，DeviceAtlas.bundle檔案會隨附於軟體與檔案描述檔（softdocs描述檔）的升級套件中，位址為：

[!DNL Server Packages > v6.00 > Server_6.00.zip]

DeviceAtlas.bundle檔案會解壓縮至[!DNL Server\Lookups\DeviceAtlas]。

DeviceAtlas.bundle檔案應放在與DPU同步的目錄中，而與新DeviceAtlasComponent對應的DeviceAtlas.cfg檔案應放在同步主版的「處理伺服器的元件」目錄中。 當DeviceAtlas.bundle檔案變更時，下一個DeviceAtlas查閱呼叫將會根據更新的API和／或JSON檔案取得結果。

## 修改Transformation.cfg檔案{#section-394823348f5740028666e62e2bd42754}

DeviceAtlas轉換將不再需要指定JSON檔案的路徑。 在transformation.cfg檔案中定義的任何舊版DeviceAtlasTransformation都不應再包含指向模糊化JSON檔案的File參數。

此示例Transformation.cfg檔案顯示應刪除的File參數，以避免混淆。 （留在那裡不會造成傷害，但只會造成潛在的混淆，因為它會被忽略。）

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

這是DeviceAtlas.cfg檔案中所需之[!DNL component]引數的範例。

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

從「描述檔同步化」功能的角度，此DeviceAtlas.bundle檔案將視為組態檔。 此外，JSON資料和DLL將用於元件層級，而非個別轉換層級。

新的DeviceAtlasComponent在啟動時會找出。bundle整合、將JSON檔案解模糊化至記憶體、將檔案擷取至暫存目錄，並載入適合執行平台的DLL。 此元件還監視對包檔案的更改，並在更改時自動重新載入DLL和。cfg檔案。

## 執行DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

正確的配置在轉換所需的時間上有很大不同。 轉換可設定為每個作業的每位訪客只執行一次，讓DeviceAtlas加速處理。

**如果使用Log Processing.cfg進行部署**:

執行兩次轉換。

1. 只查找[!DNL mobile id]欄位，然後
1. 建立條件以忽略[!DNL mobile id]，然後查看其餘欄位。

**如果使用Transformation.cfg進行部署**:

如上述「記錄處理」中的步驟1所述部署，或使用跨列來支援條件設定。

* 交叉行(Cross-Rows)-抓取上一個會話鍵。 然後識別目前的工作階段金鑰是否與使用交叉列的工作階段金鑰不同。 如果是，則DeviceAtlas轉換將僅在每個作業的一個記錄上執行。
