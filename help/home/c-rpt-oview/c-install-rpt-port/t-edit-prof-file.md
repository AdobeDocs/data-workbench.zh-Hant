---
description: 若要指定要在報表入口網站中使用的描述檔，您必須設定profiles.xml檔案。
solution: Analytics
title: 編輯Profiles.xml檔案
topic: Data workbench
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 編輯Profiles.xml檔案{#edit-the-profiles-xml-file}

若要指定要在報表入口網站中使用的描述檔，您必須設定profiles.xml檔案。

文 [!DNL profiles.xml] 件位於您指定用於輸出的資料夾中。 依預設，它位於\*PortalName*\PortalFiles\Output folder中。

**要將配置檔案名添加到profiles.xml檔案**

1. 在運行IIS的電腦上，在文本編輯器( [!DNL profiles.xml] 如記事本)中開啟檔案。
1. 為入口網站中的每個項目新增 [!DNL Profile] 描述檔元素和標籤，如下列範例所示：

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <PROFILES>
     <PROFILE>
       <NAME>Product Sales</NAME>
     </PROFILE>
     <PROFILE>
       <NAME>Product Marketing</NAME>
     </PROFILE>
   </PROFILES>
   ```

1. 儲存並關閉檔案。
