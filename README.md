function onOpen() {
  var ui = SpreadsheetApp.getUi();
  var menu = ui.createMenu('自訂功能');
  menu.addItem('隱藏下載選項', 'hideDownloadMenu');
  menu.addToUi();
}

function hideDownloadMenu() {
  var sheet = SpreadsheetApp.getActiveSheet();
  var menu = sheet.getRange('A1').getDataValidation();
  if (menu) {
    menu.clearValidation();
  }
}
