---
description: 在用戶端和伺服器之間通訊時加密密碼和其他字串。
title: 字串加密
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
exl-id: 43696ff1-3153-4d85-b9a9-c2752dd2c29a
translation-type: ht
source-git-commit: 233b04c65a45d3f92b8670bc244b907dc198b51d
workflow-type: ht
source-wordcount: '268'
ht-degree: 100%

---

# 字串加密{#string-encryption}

在用戶端和伺服器之間通訊時加密密碼和其他字串。

在 Data Workbench 用戶端 (工作站) 和伺服器之間通訊時，您可以儲存具有 *EncryptedString* 類型的 Value 參數 (例如密碼)。這會隱藏參數，並將字串與傳回的對應金鑰儲存至伺服器的 *Windows Credential Store*。這主要儲存匯出時使用的認證，但是可用於加密任何參數。

* 在 Server\**EncryptStrings** 新增了新檔案夾。

   這是您將設定檔設定為加密字串的位置。

* 在 Server\Component\**EncryptedStrings.cfg** 新增了新設定檔。

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   此檔案輪詢 *Server*\*EncryptStrings* 檔案夾以尋找加密設定檔。

**若要加密字串**：

1. 為字串建立 **EncryptedStrings.cfg** 設定檔，其欄位設定如下：

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *Value* - 此欄位包含須加密的純文字字串。

      這僅是伺服器端加密。*Value* 設定僅在伺服器電腦上加密。

   * *Name* - 此欄位包含識別加密字串的值。
   * *EncryptValue* - 此欄位在輸入設定檔中將保留空白。加密值將傳回至此欄位。

   您可以為不同欄位新增多個 **NameEncryptValuePair** 值，以進行加密。

   >[!NOTE]
   >
   >所有空白的 Value 欄位都將移除。

1. 將 **EncryptedStrings.cfg** 檔案儲存至 Server\**EncryptStrings** 檔案夾。

**輸出檔案**

將產生一個與輸入檔案同名的輸出檔案，其名稱為 &lt;*filename*>.*encrypted* (副檔名)。例如，如果輸入檔案名為 *sample.cfg*，則輸出檔案名為 *sample.cfg.encrypted*。
