---
description: 第一步是在儀表板伺服器上啟用IIS角色。
solution: Analytics
title: 啟用IIS
topic: Data workbench
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 啟用IIS{#enabling-iis}

第一步是在儀表板伺服器上啟用IIS角色。

1. 在下 **[!UICONTROL Administrative Tools]**&#x200B;面，開啟 **[!UICONTROL Server Manager]**。
1. 按一下右鍵窗口左側部分中的「角色」(Roles)菜單項 **[!UICONTROL Server Manager]** 目。
1. 選擇 **[!UICONTROL Add Roles]**.
1. 選 **[!UICONTROL Web Server (IIS)]** 擇並繼續 **[!UICONTROL Add Roles Wizard]**。 請確定已啟用下列角色服務：

   | 常見HTTP功能 |
   |---|
   | 靜態內容 |
   | 預設檔案 |
   | 目錄瀏覽 |
   | HTTP錯誤 |
   | HTTP重新導向 |

   | 應用程式開發 |
   |---|
   | ASP.NET |
   | .NET擴充性 |
   | ISAPI擴充功能 |
   | ISAPI篩選 |

   | 運行狀況和診斷 |
   |---|
   | HTTP記錄 |
   | 記錄工具 |
   | 請求監控器 |
   | 描圖 |
   | 自訂記錄 |

   | 安全性 |
   |---|
   | 基本驗證 |
   | Windows驗證 |
   | URL驗證 |
   | 請求篩選 |
   | IP和網域限制 |

   | 管理工具 |
   |---|
   | IIS管理控制台 |
   | IIS管理指令碼和工具 |
   | 管理服務 |

1. 按照嚮導完成安裝。
