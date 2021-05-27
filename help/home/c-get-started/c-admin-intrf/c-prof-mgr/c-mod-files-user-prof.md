---
description: 您可以使用「設定檔管理員」來下載您要修改的檔案。
title: 修改使用者設定檔中的本機檔案
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# 修改使用者設定檔中的本機檔案{#modify-local-files-in-the-user-profile}

您可以使用「設定檔管理員」來下載您要修改的檔案。

您可能希望下載檔案以用檔案的原始版本覆蓋現有的本地檔案，或開啟、查看和修改無法從工作區菜單訪問的檔案。

**若要下載檔案**

1. 在[!DNL Profile Manager]中，開啟必要的資料夾和子資料夾以找到要下載的檔案。
1. 按一下右鍵檔案名稱旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。

   >[!NOTE]
   >
   >配置([!DNL .cfg])、維([!DNL .dim])和度量([!DNL .metric])檔案可以直接在配置檔案夾中編輯並保存到伺服器，而無需將它們本地化並單獨保存到伺服器。 只需按一下右鍵檔案名稱旁的複選標籤，然後按一下工作站&#x200B;**中的&#x200B;**[!UICONTROL Open]**>**。

將檔案下載到本地電腦後，[!DNL User]列中會顯示一個複選標籤，表示該檔案的本地副本位於電腦的User\*profile name*資料夾中。 請注意，勾號的顏色與&#x200B;*設定檔名稱*&#x200B;欄中的勾號顏色相同。 這表示本地檔案的修改日期和時間與&#x200B;*配置檔案名稱*&#x200B;資料夾中的檔案相同。

**修改檔案的方式**

1. 按一下右鍵[!DNL User]列中檔案名旁的複選標籤。
1. 視您要編輯檔案的方式而定，按一下下列其中一個功能表選項：

   * **[!UICONTROL Open]** >  **[!UICONTROL in workstation]** (如果您正在編輯工 [!DNL .vw] 作區中的 [!DNL .cfg] 檔案或檔案)。

   * **開啟** > **。編輯器**（如果編輯.vw檔案以添加新參數）。

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** 如果要開啟文字檔案，或需要將新參數新增至檔 [!DNL .cfg] 案。

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** 如果要開啟電腦上檔案所在的資料夾

1. 視需要編輯檔案，然後儲存檔案。

在[!DNL Profile Manager]中，請注意，您編輯的檔案的[!DNL User]欄中的勾號已變更顏色。 這表示本機檔案現在與&#x200B;*設定檔名稱*&#x200B;資料夾中的版本不同。 如有必要，您可以將修訂版本的檔案發佈到設定檔，供使用此設定檔的其他使用者使用。
