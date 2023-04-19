prev :-[[Dashboards]]
next :-

#google-spreadsheets
#data-analytics-tools

## Errors 

**#DIV/0!**

A formula is trying to divide a value in a cell by 0 (or an empty cell with no value)

=B2/B3, when the cell B3 contains the value 0

**#ERROR!**

(Google Sheets only)  Something can’t be interpreted as it has been input. This is also known as a parsing error.

=COUNT(B1:D1 C1:C10) is invalid because the cell ranges aren't separated by a comma

**#N/A**

A formula can't find the data

The cell being referenced can't be found

**#NAME?**

The name of a formula or function used isn't recognized

The name of a function is misspelled

**#NUM!**

The spreadsheet can't perform a formula calculation because a cell has an invalid numeric value

=DATEDIF(A4, B4, "M") is unable to calculate the number of months between two dates because the date in cell A4 falls after the date in cell B4

**#REF!**

A formula is referencing a cell that isn't valid

A cell used in a formula was in a column that was deleted

**#VALUE!**

A general error indicating a problem with a formula or with referenced cells

There could be problems with spaces or text, or with referenced cells in a formula; you may have additional work to find the source of the problem.

## Formulas 

-   A formula is a set of instructions used to perform a calculation using the data in a spreadsheet.
=(C2+B2+D3)/2
=(C2)
= ($C$2) - Direct reference 
= (E2-D2)/D2



## Functions 
-   A function is a preset command that automatically performs a specific process or task using the data in a spreadsheet.

1. COUNTIF(RANGE, COND)
2. COUNT(RANGE)
3. DATEDIF()
4. SUM(RANGE1,RANGE2,..) / AVG / COUNT / MIN / MAX
5. VLOOKUP(search_key, range, index, [is_sorted])
Range - C3:F3

-   Relative references (cells referenced without a dollar sign, like A2) will change when you copy and paste the function into a different cell. With relative references, the location of the cell that contains the function determines the cells used by the function.
    
-   Absolute references (cells fully referenced with a dollar sign, like $A$2) will not change when you copy and paste the function into a different cell. With absolute references, the cells referenced always remain the same.
    
-   Mixed references (cells partially referenced with a dollar sign, like $A2 or A$2) will change when you copy and paste the function into a different cell. With mixed references, the location of the cell that contains the function determines the cells used by the function, but only the row or column is relative (not both).
    
-   In spreadsheets, you can press the F4 key to toggle between relative, absolute, and mixed references in a function. Click the cell containing the function, highlight the referenced cells in the formula bar, and then press F4 to toggle between and select relative, absolute, or mixed referencing.