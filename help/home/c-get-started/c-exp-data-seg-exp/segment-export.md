---
description: 使用區段匯出精靈匯出區段
title: 區段匯出精靈
uuid: 705bdf00-54e5-4992-8978-91afda8c7543
exl-id: 6f42c5c6-a158-4ddd-8949-4ef55a44ed1c
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 6%

---

# 區段匯出精靈{#segment-export-wizard}

使用區段匯出精靈匯出區段

區段匯出精靈提供設定和匯出區段的逐步程式，而非從詳細資料表](https://experienceleague.adobe.com/docs/data-workbench/using/client/export-data/c-sgmt-expt.html)匯出區段的[。

## 使用精靈匯出區段 {#section-b30f2699dbc7490bad18512b91cb0cb3}

要開啟嚮導，請在工作區中按一下右鍵，然後選擇&#x200B;**Admin** > **嚮導** > **段導出嚮導**。

>[!NOTE]
>
>只會擷取開啟精靈前所套用的區段。 此外，從精靈建立的區段匯出無法產生外部命令。

1. 選取要新增至匯出的維度和量度的各個父層級。

   顯示的層級取決於選取的設定檔。 您可以根據設定檔選取多個維度層級。

   ![](assets/seg_wizard_1.png)

1. 按&#x200B;**「下一步」**。
1. 選取所選層級的Dimension和量度。

   例如，選取「頁面檢視」作為父層級後，您就可以選取可匯出的子維度和量度。

1. 按&#x200B;**「下一步」**。

   ![](assets/seg_wizard_2.png)

   ![](assets/seg_wizard_2_1.png)

1. 選擇導出格式並輸入導出檔案的名稱。

   ![](assets/seg_wizard_3.png)

   CSV、TSV、區段匯出和具有標題類型的區段匯出不需要額外設定。 不過，設定檔與對象匯出、自訂記錄服務和Adobe Target匯出需在步驟3中設定。 例如，請參閱「設定檔與對象匯出」的設定欄位。 配置這些導出類型，然後按一下&#x200B;**Next**。

   ![](assets/seg_wizard_3_1.png)

   ![](assets/seg_wizard_3_2.png)

   ![](assets/seg_wizard_3_3.png)

1. 配置所選導出類型。

   標題(Header) — 如果標題為True，則為&#x200B;**輸出檔案**&#x200B;欄位命名。

   逸出欄位 — 設定為&#x200B;**True**&#x200B;或&#x200B;**False**。

   欄位順序(Order of Fields) — 選擇一個欄位，然後上移或下移以設定導出檔案中的順序。

   ![](assets/seg_wizard_4.png)

   按&#x200B;**「下一步」**。

1. 在此對話框中查看級別和已應用的篩選器。 按一下&#x200B;**「下一步」**。![](assets/seg_wizard_5.png)

1. 如果選取了&#x200B;**CSV**、**TSV**、**區段匯出**&#x200B;或&#x200B;**標題為的區段匯出，則有三個選項：**

   一般導出 — 輸出檔案將由伺服器在「伺服器/導出」資料夾中生成。

   ![](assets/seg_wizard_6.png)

   FTP匯出 — 輸出檔案將傳輸至選取的伺服器。 （將從FTPServerInfo.cfg檔案中選擇伺服器的清單。）

   ![](assets/seg_wizard_6_1.png)

   SFTP匯出 — 輸出檔案將安全地傳輸至選取的伺服器。

1. 按一下&#x200B;**「下一步」**。

   **注意：** 如果選取的匯出類型 **為「設定檔與對象匯出」**、 **「自訂記錄服務」**&#x200B;和 **「Adobe Target匯出」**，則文字將會根據選取的匯出為靜態。

1. 設定排程參數。

   **一** 個分鏡可設為True或False。

   **按一** 下「進階排程設定」按鈕，即可開啟或關閉進階排程。

   ![](assets/seg_wizard_7.png)

   與從「詳細資料」表格匯出一樣，如果開啟「進階設定」，則會捨棄一次點擊。 按&#x200B;**「下一步」**。

1. 預覽匯出檔案，然後按一下&#x200B;**執行匯出**。

   ![](assets/seg_wizard_8.png)

   ![](assets/seg_wizard_8_1.png)

使用嚮導可以使用以下導出類型：

**區段匯出類型**

* 通用
* FTP
* SFTP

**帶標題的區段匯出**

* 通用
* FTP
* SFTP

**CSV匯出**

* 通用
* FTP
* SFTP

**TSV匯出**

* 通用
* FTP
* SFTP
