---
description: 在客戶端和伺服器之間通信時加密口令和其他字串。
title: 字串加密
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 字串加密{#string-encryption}

在客戶端和伺服器之間通信時加密口令和其他字串。

當資料工作台用戶端（工作站）和伺服器之間通訊時，您可以儲存值參數（例如密碼）與加密字串類 *型*。 這會隱藏參數，並將字串儲存至伺服器上 *Windows憑證存放區* ，並傳回對應的金鑰。 這主要儲存匯出時使用的憑證，但可用於加密任何參數。

* 在Server\**EncryptStrings**中新增了新資料夾。

   這是您將配置檔案設定為加密字串的位置。

* 在Server\Component\**EncryptedStrings.cfg**新增了新的設定檔。

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   此檔案輪詢 *Server*\*EncryptStrings*資料夾以查找加密配置檔案。

**要加密字串**:

1. 為字 **** 串建立EncryptedStrings.cfg組態檔，其欄位設定如下：

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *值* -此欄位包含需要加密的純文字檔案字串。

      這僅是伺服器端加密。 Value *設定僅* 在伺服器電腦上加密。

   * *名稱* -此欄位包含標識加密字串的值。
   * *EncryptValue* —— 此欄位在輸入配置檔案中將保留為空。 此欄位將傳回加密的值。
   您可以為不同 **的欄位新增多個NameEncryptValuePair值** ，以進行加密。

   >[!NOTE]
   >
   >所有空值欄位都將被刪除。

1. 將 **EncryptedStrings.cfg檔案儲存至Server** \**EncryptStrings**資料夾。

**輸出檔案**

將生成一個與輸入檔案同名的輸出檔案，其名稱為&lt;*filename*>。*加密擴充* 。 例如，如果輸入檔名為 *sample.cfg* ，則輸出檔名 *sample.cfg.encrypted*。
