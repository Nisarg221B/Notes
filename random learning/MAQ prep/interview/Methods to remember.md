### SQL

STRING
- substring( string, a, b) - substr from a to b
- LTRIM - left trim
- RTRIM - right trim
- length 
- INSTR (string , pattern) - returns position 
- Replace(string, 'a' , 'b') - replaces a with b
- Concat(string 1 , string 2 , string 3)

DATE
- YEAR(date) -> returns year from the date in int
- MONTH(date) -> returns month from the date

LIMIT Offset(optional) , row_count 
LIMIT 5,10 -> 10 rows starting from row 6
LIMIT 5 -> 5 rows from top
### Strings

- string to int  -> *stoi , stoll , stol* 
- int to string -> *to_string(int a);*
- reverse string -> *reverse(s.begin(), s.end());*

Note : reverse takes bidrectional iterator which implies it can also reverse a vector.


### Stack

*s.top()*  
*s.push()* - do not return anything
*s.pop()* - do not return anything
s.empty() - checks if stack is empty
s.size() - size of the stack


