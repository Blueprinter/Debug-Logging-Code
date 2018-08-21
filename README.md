# Debug-Logging-Code

# NOTE: I've made lots of changes, and the code that is posted is currently not the most recent code

Apps Script Debug Logging

The code in the file named "Code GS" is to log variable values from Google Apps Script to a Google Spreadsheet

FEATURES:
* Short function name for logging - Logger.log or console.log is long - zz8 is short
* Type the variable name as a string - the variable value is looked up from the string
* Log each of your function variable values to different sheet tabs
* Null, undefined, empty strings, and numbers correctly indicated in the spreadsheet
* Stringifys JSON objects and arrays before saving to the spreadsheet cell
* Test for date objects and displays the value correctly

SET UP:
* Create a new Google Spreadsheet for receiving the logging output
* Put the file ID of the Google Spreadsheet into the Apps Script code
var SS_ID = 'PUT THE SPREADSHEET FILE ID HERE';
* Run a function from the code editor to get a prompt for authorizing the permissions - otherwise the code will fail

The function name is zxz

Why is the function name zxz?

The characters z and x are some of the least used characters.
The reason why I use zxz is to reduce the likelihood that a text search will result in finding content that you don't want to mistakely replace.

Why do you want to replace the characters zxz?  If you want to remove or comment out function calls to the logging function, then using search and replace is faster than manually commenting out every line of code.  But search and replace very often finds content that you do not want to replace, so if you want to use "Replace All" then you need to make sure that the characters being found are unique.

You may want to add this code as a library so that you don't need to add a new GS file to your Apps Script project for the logging code.  Also, if it's added as a library, then you can remove the library if you don't want it to be installed for your production version.

The function takes 2 parameters.  
There is no longer a need to enter the sheet tab number - all functions are put into different sheet tabs in the order that they ran

The first 3 parameters are not for anything except whatever you want written to the spreadsheet.

    function zxz(a,b,c,whichSheetTab) {

I usually put the variable name as text in the first place (parameter "a") and a variable name in the second place (parameter "b").
I put the function name in the third parameter "c"

    zxz('variable_name',variable_name,"function_name",2) {//Call function zxz and Log this value to sheet tab 2

If you add the code as a library, then you'll need to use the library identifier and then a dot and then the function name.

For example, if the library identifier was "pzp" then you would call the log function with:

    pzp.zxz('variable_name',variable_name,"function_name",2)//Call the library and the function zxz in the library

The characters pzp.zxz are very unique and therefore easy to search and replace without replacing content that you don't want changed

To use the code in a library, create a new Apps Script stand alone file, copy and paste in the code into the stand alone file, and save the apps script project.  In the File Menu, choose "Manage Versions" and save a new version. In the File menu, choose "Project properties"  Copy the "Project Key (Deprecated)

https://developers.google.com/apps-script/guides/libraries#creating_a_library

In the Apps Script project where you want to use the logging code, click the "Resources" menu and choose "Library"  Enter the Key into the field at the bottom of the window, and click "Add".  Make sure to choose the version number, and put in an identifier.

To avoid needing to enter the function name (parameter c) in every function call, I add a variable associated with a function in every function.

    function myFunction() {
      var myVar;
      var zz8 = function(a,b,c) {if (!b) {pzp(a,eval(a),'myFunction');} else {pzp(a,b,'myFunction')}}
      //Log the values from this function to a spreadsheet - The pzp function will automatically put each function output
      //into subsequent Sheet tabs - in the order of the stack
  
      myVar = new Date();
  
      zz8('myVar') //Call the function zz8 to log both the variable name and variable value to the spreadsheet
    }

Setting things up in the above way makes each function call shorter, only two parameters need to be entered, and they are both identical except for the single quotes around the first parameter.
