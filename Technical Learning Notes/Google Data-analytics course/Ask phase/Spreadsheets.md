


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