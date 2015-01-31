# The different counting functions

`=count(RANGE)`
Counts **only** numbers in RANGE.  This will **not** count characters.  [Offical documentation](http://office.microsoft.com/en-us/excel-help/count-HP005209026.aspx).


`=count(RANGE,VALUE)`
Counts **only** numbers equal to VALUE in RANGE.  [Offical documentation](http://office.microsoft.com/en-us/excel-help/count-HP005209026.aspx).


`=counta(RANGE)`
Counts all the non-blank cells (numbers/characters/dates/etc.) in RANGE.  [Official documentation](http://office.microsoft.com/en-us/excel-help/counta-HP005209027.aspx).


`=countif(RANGE,CRITERIA)`
This is my preferred "count" function, because you can put anything in CRITERIA-- **including a character string**, which makes it useful to count "Pass" or "Fail" in a spreadsheet.  You can also use greater than/less than criteria by putting, for example, ">VALUE" or ">=VALUE" in CRITERIA; note that the double quotes are necessary!  Wildcards can also be used, but I haven't needed that functionality yet.  [Official documentation](http://office.microsoft.com/en-us/excel-help/countif-HP005209029.aspx).



# How I generated my weekly product yield plots using VBA and several complicated Excel formulas

(Step 0: Download five separate spreadsheets of the weekly yield from the company-wide database.)

## Step 1: Import data using the steps in this macro (modified from [this](http://stackoverflow.com/questions/19351832/vba-copy-from-one-workbook-and-paste-into-another) StackOverflow question).

### Inital lines:

(Frankly, no idea why the first line is there, but it works...)

<pre><code>Application.Calculation = xlManual
Dim data As Workbook
Dim main As Workbook
Set main = ActiveWorkbook
</code></pre>

### Sub-step A:







