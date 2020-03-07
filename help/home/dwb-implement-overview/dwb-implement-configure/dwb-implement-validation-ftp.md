---
description: 本快速指南提供驗證內部和外部FTP設定所需的最低步驟。
title: 內部和外部FTP伺服器的驗證
uuid: bc381c1d-df27-4009-920b-1a804b36c204
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# 內部和外部FTP伺服器的驗證{#validation-of-internal-and-external-ftp-servers}

本快速指南提供驗證內部和外部FTP設定所需的最低步驟。

當Adobe內部顧問／架構師必須連線至FTP網站才能上傳或下載檔案時，會使用內部FTP，而外部FTP則主要供您做為上傳必要資料檔案的使用者。

如需設定FTP伺服器的詳細資訊，請參閱檔案 [傳輸通訊協定](https://docs.adobe.com/content/help/en/analytics/export/ftp-and-sftp/ftp-overview.html)。

## 驗證步驟——外部FTP {#section-24428111b5c542ce81a765cd63424b97}

1. 開啟命令提示符。 （Windows+R並鍵入cmd）
1. Type ftp `<ftp server>`
1. 提供使用者名稱和密碼。 ![](assets/dwb_impl_ftp1.png)

1. 更改可移動某些檔案的本地目錄。 使用以下命令：

[!DNL ftp> lcd C:\Users\andixit\Desktop]

本地目錄 [!DNL C:\Users\andixit\Desktop]。

1. 將檔案從本地複製到遠程位置。 ![](assets/dwb_impl_ftp2.png)

1. 從遠程伺服器註銷。 （使用下方命令）

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>另一個驗證FTP的方式是使用Filezilla。 提供主機名、用戶名、密碼和埠。 面板的右側是遠程站點，左側是本地站點。 若要驗證FTP從本機拖放檔案至遠端網站和v.v。

![](assets/dwb_impl_ftp3.png)

## 驗證步驟——內部FTP {#section-b1f7a789ad6848cf9027f7953d81066e}

可依照上述步驟來驗證來自任何Adobe伺服器的內部ftp。
