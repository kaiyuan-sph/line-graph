# line-graph

Add this code in the google sheet apps script 
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
