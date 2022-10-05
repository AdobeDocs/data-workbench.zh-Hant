---
description: 若要指定您要在Report Portal中使用的設定檔，您必須設定profiles.xml檔案。
title: 編輯 Profiles.xml 檔案
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---

# 編輯 Profiles.xml 檔案{#edit-the-profiles-xml-file}

{{eol}}

若要指定您要在Report Portal中使用的設定檔，您必須設定profiles.xml檔案。

此 [!DNL profiles.xml] 檔案位於您為輸出指定的資料夾中。 預設情況下，它駐留在\*PortalName*\PortalFiles\Output資料夾中。

**將配置檔案名添加到profiles.xml檔案**

1. 在運行IIS的電腦上，開啟 [!DNL profiles.xml] 檔案（如記事本）。
1. 為每個 [!DNL Profile] 在您的入口網站中，如下列範例所示：

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
