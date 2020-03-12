---
description: 您現在可以使用FTP和SFTP通訊協定，將區段檔案從用戶端（工作站）匯出至伺服器，使用CSV、TSV、區段匯出和區段匯出（含標題）。
title: 使用S/FTP傳送匯出區段
uuid: 4d654368-cbf7-4e7f-8ab9-82f4e0261ac6
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# 使用S/FTP傳送匯出區段{#export-a-segment-using-s-ftp-delivery}

您現在可以使用FTP和SFTP通訊協定，將區段檔案從用戶端（工作站）匯出至伺服器，使用CSV、TSV、區段匯出和區段匯出（含標題）。

**設定S/FTP匯出設定檔案**

要設定導出配置，添加了兩個新的導出配置檔案以設定FTP或SFTP連接，允許從 *FTPServerInfo.cfg檔案中選擇伺服器詳細資訊，並從*** FTPUserCredentials資料夾中選擇憑據（與命令參數中提供的伺服器名稱相對應）。

* 設定 **FTPServerInfo.cfg檔** 。

   輸入FTP伺服器資訊並設定允許從工作站進行的連接重試。 從工作站或位於[!DNL Server\Addresses\Export\]檔案的伺服器進行編 **[!DNL FTPServerInfo.cfg]** 輯。

   ```
   FTP Servers = vector: 1 items 
     0 = ftpServerInfo:  
       Address = string:  
       Name = string:  
       Port = int: 21 
   Connect Retries = vector: 1 items 
     0 = connectServerRetries:  
       Retries = int: 0 
       Server Name = string:
   ```

* 設定 **FTPUserCredentials.cfg檔案** 。

   輸入用戶憑據以使用[!DNL Server\Admin\Export\]檔案連接到服 **[!DNL FTPUserCredentials.cfg]** 務器。 此檔案包含連接到伺服器所需的用戶憑據，只能從伺服器編輯，不能從工作站（客戶端）編輯。

   ```
   FTP User Credentials = vector: 1 items 
     0 = ftpUserCredInfo: 
       User Name = string:  
       User Password = EncryptedString:  
       Server Name = string:  
       Public Key Path = string:  
       Private Key Path = string:  
       Passphrase = EncryptedString:
   ```

   >[!NOTE]
   >
   >確保為驗證生成的SSH密鑰的格式與使用SSH Keygen命令時生成的密鑰的格式相同。
   >
   >使用keygen生成SSH密鑰的示例：
   >
   >```
   >ssh-keygen -t rsa -b 4096 -C "<label>"
   >```

   FTPUserCredentials.cfg檔案中有6個參 **數是各種FTP或SFTP傳輸所需的** 。

   1. *使用者名稱*
   1. *使用者密碼*
   1. *伺服器名稱*
   1. *公共密鑰路徑*
   1. *私密金鑰路徑*
   1. *密碼短語*
   <table id="table_4EB416DC770D4D1AA4FAD9676C0D680C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 通訊協定 </th> 
      <th colname="col2" class="entry"> 參數 </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>FTP </p> </td> 
      <td colname="col2"> <p>設定參數1、2、3。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>使用密碼驗證的SFTP </p> </td> 
      <td colname="col2"> <p>在傳輸使用口令驗證（命令參數中的-p）時設定參數1、2、3。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>使用密鑰驗證的SFTP </p> </td> 
      <td colname="col2"> <p>當傳輸使用密鑰驗證（命令參數中的-k）時，請設定參數1、2、3、4、5、6。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

**設定FTP和SFTP匯出指令**

1. 開啟匯出表格。

   在工作站中，按一下右鍵「詳 *細資訊表* 」並選擇其中一種導出類型：CSV、TSV、段導出或帶標題的段導出。 或從命令 [!DNL .export] 提示符開啟檔案並進行編輯(請參 [閱設定匯出區段](../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372))。

1. 在「命 *令* 」(Command)欄位中，將其設定為指嚮導出執行檔：

   ```
   ExportIntegration.exe
   ```

1. 為所需 *的協定和驗證設定* 「命令參數」欄位，如下所示：

   **FTP**

   ```
   <Command Arguments> set to  
   <ftp "%file%" ServerName ServerDestinationPath>
   ```

   ![](assets/FTP_Command_arguments.png)

   **SFTP** （如果使用密碼進行驗證）

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -p>
   ```

   **SFTP** （如果使用金鑰進行驗證）

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -k>
   ```

   ![](assets/SFTP_command_arguments.png)

所有命令參數都是必需的，需要按如所示輸入。

## 使用私用／公用金鑰進行S/FTP匯出 {#section-0534424d79a54a47b82594cfa7b3c17f}

若要使用私密金鑰和公用金鑰實作FTP和SFTP匯出，請將設定檔案置於下列資料夾中：

* 將 **FTPServerInfo.cfg** 置於資料 [!DNL Server/Addresses/Export/] 夾中。
* 將 **FTPUserCredentials.cfg** 置於資料 [!DNL Server/Admin/Export/] 夾中。

FTPServerInfo.cfg檔案中包 **含6個參數** :

1. *使用者名稱*
1. *使用者密碼*
1. *伺服器名稱*
1. *公共密鑰路徑*
1. *私密密鑰路徑* —將私密密鑰路徑放置在配置檔案中，不帶副檔名，例如：

[!DNL Private Key Path = string: E:\\Server\\campaign\\campaignprivatekey]

1. *密碼短語*

FTP使用參數1、2和3。

當傳輸使用密碼驗證時，SFTP使用參數1、2和3。

當使用金鑰驗證完成傳輸時，SFTP會使用所有6個參數。 例如，如果您使用金鑰進行驗證：

[!DNL 'Command Arguments' = sftp "%file%" ServerName ServerDestinationPath -k]

配置檔案必須位於正確的位置。

>[!NOTE]
>
>公共密鑰需要指向 **.pem檔案** ，而不是指向資料夾位置。 您可以使用SSH密鑰生成功能從Cygwin等應用程式建立密鑰。 （Putty會以。ppk格式產生不支援的金鑰。）
