---
description: 透過使用參考頁面標籤來加速收集連結點按次數的步驟。
title: 追蹤連結點按次數
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
exl-id: 0cb743e6-5c6e-4f80-bc77-83d1e706c92b
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---

# 追蹤連結點按次數{#tracking-link-clicks}

透過使用參考頁面標籤來加速收集連結點按次數的步驟。

透過[!DNL Reference Page Tag]的部署，可收集表示訪客在瀏覽特定頁面時所點按之連結（或href值）的測量資料。 通常，此集合不涉及將其他連結識別碼實施至您的HTML頁面。

若要透過使用[!DNL Reference Page Tag]來加速收集連結點按次數，請完成下列步驟：

1. 將以下代碼複製到名為[!DNL zig.js]的現有檔案中：

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

1. 將名為[!DNL zag2.gif]的1像素影像檔案建立或放置到Web伺服器上的目錄。
1. 修改[!DNL lc.src]變數，以參考參考[!DNL zag2.gif]檔案的網站適當網域。

1. 確保為[!DNL zag.gif]和[!DNL zig.js]檔案建立適當的快取控制標頭。

1. 在您要從中收集連結點按值的HTML檔案中，必須修改[!DNL Reference Page Tag Execution Call]以通知[!DNL Page Tag Execution Script]以擷取該頁面的連結點按。 若要這麼做，請將vlc變數值變更為「1」，如下列程式碼範例中強調顯示：

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE
var v = {};
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_ln= | 表示曝光促銷活動的值 | v_ln=&quot;關於%20Us&quot; |
