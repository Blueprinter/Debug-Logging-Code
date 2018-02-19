# Debug-Logging-Code
Apps Script Debug Logging

FEATURES:
* Log each of your function variable values to different sheet tabs
* Null, undefined, empty strings, and numbers correctly indicated in the spreadsheet

SET UP:
* Create a new Google Spreadsheet for receiving the logging output
* Put the file ID of the Google Spreadsheet into the Apps Script code
var SS_ID = 'PUT THE SPREADSHEET FILE ID HERE';

The function name is zxz

Why is the function name zxz?

The characters z and x are some of the least used characters.
The reason why I use zxz is to reduce the likelihood that a text search will result in finding content that you don't want to mistakely replace.

Why do you want to replace the characters zxz?  If you want to remove or comment out function calls to the logging function, then using search and replace is faster than manually commenting out every line of code.  But search and replace very often finds content that you do not want to replace, so if you want to use "Replace All" then you need to make sure that the characters being found are unique.

You may want to add this code as a library so that you don't need to add a new GS file to your Apps Script project for the logging code.  Also, if it's added as a library, then you can remove the library if you don't want it to be installed for your production version.

The function takes 4 parameters.  
The 4th parameter is what which sheet tab you want the values put into.

The first 3 parameters are not for anything except whatever you want written to the spreadsheet.

function zxz(a,b,c,whichSheetTab) {

I usually put the variable name as text in the first place (parameter "a") and a variable name in the second place (parameter "b").
I put the function name in the third parameter "c"

zxz('variable_name',variable_name,"function_name",2) {//Call function zxz and Log this value to sheet tab 2

If you add the code as a library, then you'll need to use the library identifier and then a dot and then the function name.

For example, if the library identifier was "pzp" then you would call the log function with:

pzp.zxz('variable_name',variable_name,"function_name",2)//Call the library and the function zxz in the library

The characters pzp.zxz are very unique and therefore easy to search and replace without replacing content that you don't want changed

To avoid needing to enter the function name (parameter c) in every function call, I add a variable associated with a function in every function.

function myFunction() {
  var myVar;
  var zz8 = function(a,b,c) {pzp.zxz(a,b,'myFunction',3)}//Log the values from this function to a spreadsheet in sheet tab 3
  
  myVar = new Date();
  
  zz8('myVar',myVar) //Call function to log to the spreadsheet
}

Setting things up in the above way makes each function call shorter, only two parameters need to be entered, and they are both identical except for the single quotes around the first parameter.
