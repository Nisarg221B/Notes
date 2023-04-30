#data-cleaning

next :- [[Change log]]
prev :- [[proxy data]]


advance SQL functions
#sql
- cast

![[Screenshot 2023-04-26 at 6.22.19 PM.png|500]]

- Coalesce - to skip null values
![[Screenshot 2023-04-26 at 6.27.18 PM.png|500]]

- Concat - to create new unique keys
![[Screenshot 2023-04-26 at 6.28.00 PM.png|500]]

- Case 
![[Screenshot 2023-04-26 at 7.13.55 PM.png|500]]
![[Screenshot 2023-04-26 at 7.14.37 PM.png|500]]

- Extract
- count(distinct x )
- select columnA , columnB\*columnC as Product       - operators
- For temporary table use 
with temp_table as (
	select *
	From ....
)
the second way to create temp table  - Select into command
![[Screenshot 2023-04-30 at 2.00.17 PM.png | 200]]

![[Screenshot 2023-04-30 at 2.01.27 PM.png | 300]]


## Correct the most common problems

Make sure you identified the most common problems and corrected them, including:

-   **Sources of errors**: Did you use the right tools and functions to find the source of the errors in your dataset?
-   **Null data**: Did you search for NULLs using conditional formatting and filters?
-   **Misspelled words**: Did you locate all misspellings?
-   **Mistyped numbers**: Did you double-check that your numeric data has been entered correctly?
-   **Extra spaces and characters**: Did you remove any extra spaces or characters using the **TRIM** function?
-   **Mismatched data types**: Did you check that numeric, date, and string data are typecast correctly?
-   **Messy (inconsistent) strings**: Did you make sure that all of your strings are consistent  and meaningful?
-   **Messy (inconsistent) date formats**: Did you format the dates consistently throughout your dataset?
-   **Misleading variable labels (columns)**: Did you name your columns meaningfully?
-   **Truncated data:** Did you check for truncated or missing data that needs correction?
-   **Business Logic**: Did you check that the data makes sense given your knowledge of the business?

After data cleaning process the following three things has to be verified :-
![[Pasted image 20230426193307.png | 500]]

