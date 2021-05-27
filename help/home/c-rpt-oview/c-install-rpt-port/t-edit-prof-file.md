---
description: 若要指定您要在Report Portal中使用的設定檔，您必須設定profiles.xml檔案。
title: 編輯 Profiles.xml 檔案
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---

# 編輯 Profiles.xml 檔案{#edit-the-profiles-xml-file}

若要指定您要在Report Portal中使用的設定檔，您必須設定profiles.xml檔案。

[!DNL profiles.xml]檔案位於您為輸出指定的資料夾中。 預設情況下，它駐留在\*PortalName*\PortalFiles\Output folder中。

**將配置檔案名添加到profiles.xml檔案**

1. 在運行IIS的電腦上，在文本編輯器（如記事本）中開啟[!DNL profiles.xml]檔案。
1. 為入口網站中的每個[!DNL Profile]新增設定檔元素和標籤，如下列範例所示：

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
