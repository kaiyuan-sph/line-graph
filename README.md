# line-graph
## Add this code in the google sheet apps script 

```
function doGet(e) {
  if (e.parameter.method == "line") { 
    var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("line-graph");
    var data = sheet.getDataRange().getValues();
    Logger.log(JSON.stringify(data));
    return ContentService
      .createTextOutput(e.parameter.callback + "(" + JSON.stringify(data) + ")")
      .setMimeType(ContentService.MimeType.JAVASCRIPT);
  }
}
```

  ## Add this in the HTML page where you embed the form
  ```
<p>
  <iframe frameborder="0" id="line-graph" scrolling="no" src="https://kaiyuan-sph.github.io/line-graph/" width="100%"></iframe>
</p>
<script src="/bt_files/2021/form/iframeResizer.min.js"></script>
<script>
  iFrameResize({ log: true }, '#line-graph')
</script>
  ```
