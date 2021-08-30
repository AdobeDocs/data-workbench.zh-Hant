---
description: 本快速指南提供驗證內部和外部FTP設定所需的最低步驟。
title: 驗證內部和外部 FTP 伺服器
uuid: bc381c1d-df27-4009-920b-1a804b36c204
exl-id: 8eecfda7-ffa0-458c-a518-434758344bfe
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 9%

---

# 驗證內部和外部 FTP 伺服器{#validation-of-internal-and-external-ftp-servers}

本快速指南提供驗證內部和外部FTP設定所需的最低步驟。

當Adobe內部的顧問/架構師必須連線至FTP站台以上傳或下載檔案時，會使用內部FTP，而外部FTP則主要供您作為使用者上傳所需的資料檔案。

如需設定FTP伺服器的詳細資訊，請參閱[檔案傳輸通訊協定](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-overview.html?lang=zh-Hant)。

## 驗證步驟 — 外部FTP {#section-24428111b5c542ce81a765cd63424b97}

1. 開啟命令提示符。 （Windows+R，鍵入cmd）
1. 鍵入ftp `<ftp server>`
1. 提供使用者名稱和密碼。![](assets/dwb_impl_ftp1.png)

1. 更改可移動某些檔案的本地目錄。 使用此命令：

[!DNL ftp> lcd C:\Users\andixit\Desktop]

本地目錄現在[!DNL C:\Users\andixit\Desktop]。

1. 將檔案從本地複製到遠程位置。![](assets/dwb_impl_ftp2.png)

1. 從遠程伺服器註銷。 （使用以下命令）

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>驗證FTP的另一種方式是使用Filezilla。 提供主機名、用戶名、密碼和埠。 面板的右側是遠程站點，左側是本地站點。 驗證FTP從本機拖放檔案至遠端和v.v的方式。

![](assets/dwb_impl_ftp3.png)

## 驗證步驟 — 內部FTP {#section-b1f7a789ad6848cf9027f7953d81066e}

可以依照上述步驟來驗證來自任何Adobe伺服器的內部ftp。
