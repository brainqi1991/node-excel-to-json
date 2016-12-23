## Excel2JSON
Forked From [kashifeqbal/node-excel-to-json](https://github.com/kashifeqbal/node-excel-to-json)
Fork reason:
- Deleted unuseful code.
- Use absolute file path.

Turn any xls or xlsx file into a clean JSON file or Javascript Object. This module is npm module 'XLXS'  Pure-JS cleanroom implementation from official specifications and related documents.

Supported read formats:
- Excel 2007+ XML Formats (XLSX/XLSM)
- Excel 2007+ Binary Format (XLSB)
- Excel 2003-2004 XML Format (XML "SpreadsheetML")
- Excel 97-2004 (XLS BIFF8)
- Excel 5.0/95 (XLS BIFF5)
- OpenDocument Spreadsheet (ODS)

## Install

    $ npm install my-xls-to-json

## Usage

`excel2Json(fileName, [options], callback)`

Where

  * **fileName** relative path of Excel file.
  * **options**  is a optional args `{
      convert_all_sheet: true,
      return_type: 'File',
      sheetName: ''
  }`
    * **convert_all_sheet** If this value is false, Then one sheet will processed which name would be provided
    * **return_type** Two type of return type 'File' or 'Object'
    * **sheetName** Only if convert_all_sheet=false
  * **callback** is the callback to run - `callback(error, output)`

Example
```javascript
var excel2Json = require('my-xls-to-json');
var path = require('path');

var dir = __dirname;
excel2Json(path.join(dir,'sample.xls'), function(err, output) {
    // output is the JSON Object.
});

<!-- Options -->
excel2Json('/tpm/upload_eaf9af7d6ae2b6e887325aa5e8978c94.xlsx', {
    'convert_all_sheet': false,
    'return_type': 'File',
    'sheetName': 'survey'
}, function(err, output) {

});
```
