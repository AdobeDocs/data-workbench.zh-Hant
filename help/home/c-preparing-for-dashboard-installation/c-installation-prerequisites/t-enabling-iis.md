---
description: 第一步是在控制面板伺服器上啟用IIS角色。
title: 啟用 IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# 啟用 IIS{#enabling-iis}

{{eol}}

第一步是在控制面板伺服器上啟用IIS角色。

1. 在 **[!UICONTROL Administrative Tools]**，開啟 **[!UICONTROL Server Manager]**.
1. 按一下右鍵 **[!UICONTROL Server Manager]** 窗口。
1. 選擇 **[!UICONTROL Add Roles]**.
1. 選擇 **[!UICONTROL Web Server (IIS)]** 繼續 **[!UICONTROL Add Roles Wizard]**. 請確保已啟用以下角色服務：

   | 常見HTTP功能 |
   |---|
   | 靜態內容 |
   | 預設文檔 |
   | 目錄瀏覽 |
   | HTTP錯誤 |
   | HTTP重定向 |

   | 應用程式開發 |
   |---|
   | ASP.NET |
   | .NET的擴展性 |
   | ISAPI擴充功能 |
   | ISAPI篩選器 |

   | 運行狀況和診斷 |
   |---|
   | HTTP記錄 |
   | 記錄工具 |
   | 請求監視 |
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
