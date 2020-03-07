---
description: 使用「參考頁面標籤」以方便收集「連結點按」的步驟。
solution: Analytics
title: 追蹤連結點按次數
topic: Data workbench
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 追蹤連結點按次數{#tracking-link-clicks}

使用「參考頁面標籤」以方便收集「連結點按」的步驟。

透過部署，您可 [!DNL Reference Page Tag]以收集表示訪客瀏覽特定頁面時點按之連結（或href值）的測量資料。 通常，此系列不會涉及在HTML頁面中實施其他連結識別碼。

若要透過使用來協助收集「連結點按」 [!DNL Reference Page Tag]，請完成下列步驟：

1. 將下列程式碼複製至名為的現有檔案 [!DNL zig.js]:

   ```
   //REFERENCE LINK AND FORM CLICK PAGE TAG 
   //INITIATE FUNCTIONS ONLOAD 
   function addEvent(obj, evType, fn){  
    if (obj.addEventListener){  
      obj.addEventListener(evType, fn, false);  
      return true;  
    } else if (obj.attachEvent){  
      var r = obj.attachEvent("on"+evType, fn);  
      return r;  
    } else {  
      return false;  
    }  
   } 
   addEvent(window, 'load', startCapture); 
   addEvent(window, 'load', startCapture); 
   function startCapture(){ 
   //TO CAPTURE LINK CLICKS 
     if (vlc == "1"){captureLink();} 
     //TO CAPTURE FORM FIELD CLICKS 
     if (vfc == "1"){captureForm();} 
   } 
   //BEGIN LINK CAPTURE PAGE TAG 
   function captureLink(){ 
     if (document.links[0]){ 
       if (document.links){ 
         var links = document.links, link, k=0; 
         while(link=links[k++]) { 
           link.onclick = captureLinkName; 
    } 
       } 
     } 
   } 
   function captureLinkName() { 
     var lc=new Image(); 
     this.parent = this.parentNode; 
     lc.src='zag2.gif?linkname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END LINK CAPTURE PAGE TAG 
   //BEGIN FORM CLICK CAPTURE PAGE TAG 
   function captureForm(){ 
     if (document.forms[0]) { 
       if(document.forms){ 
    for(i=0; i<document.forms[0].elements.length; i++){ 
           var forms = document.forms[0].elements[i]; 
           forms.onfocus = captureFormName; 
         } 
       } 
     } 
   } 
   function captureFormName() { 
     var fc=new Image(); 
     fc.src='zag3.gif?fieldname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END FORM CLICK CAPTURE PAGE TAG
   ```

1. 建立或置入名為1像素乘1像素的影像檔， [!DNL zag2.gif] 並放入Web伺服器上的目錄。
1. 修改變 [!DNL lc.src] 數，以參考您參考檔案所在之網站 [!DNL zag2.gif]的適當網域。

1. 確保為和檔案建立適當的快取控 [!DNL zag.gif] 制標 [!DNL zig.js] 頭。

1. 在您要收集連結點按值的HTML檔案中，必 [!DNL Reference Page Tag Execution Call] 須修改該檔案，以通知 [!DNL Page Tag Execution Script] 擷取該頁面的連結點按。 若要這麼做，請將vlc變數值變更為&quot;1&quot;，如下列程式碼範例中反白顯示：

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE 
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE 
var v = {}; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_ln= | 指示印象促銷活動的值 | v_ln=&quot;About%20Us&quot; |

