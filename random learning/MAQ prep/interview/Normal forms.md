Requiring existence of "the key" ensures that the table is in [1NF](https://en.wikipedia.org/wiki/First_normal_form "First normal form"); requiring that non-key attributes be dependent on "the whole key" ensures [2NF](https://en.wikipedia.org/wiki/Second_normal_form "Second normal form"); further requiring that non-key attributes be dependent on "nothing but the key" ensures 3NF.
## 1NF

Table is in 1NF when it follows 
- No repeating values in a group/Column
- No repeating group/Column

ex

see the below table has repeating values in group phone number

EmpID(PK) , name , Phone1 , address 
201                saghir, 532423 , ..
								342454

Solution

- we cannot have another column as Phone2 as it will violets the second condition of 1NF that table should not have multiple columns with similar kind of data.
- and we cannot add a row because of primary key

thus
- solution is to take the column out and make a new table

Table 1 -> EmpID(pk) , name, phone
Table 2 ->  phone , name or EmpID(fk)


## 2 NF

- Any non key field should entirely depend on its primary key

	- should be in 1 NF
	- No parital dependency (Occurs when there is composite key - more than one column makes up a primary key) 

ex

![[Screenshot 2023-11-23 at 8.08.43 AM.png]]

here (studentId, course) is primary key
but course also can identify the Teacher thus there is parital dependency.

name,marks are depending on both composite key column thus no parital dependency there.
but
Teacher only depended on one of the composite key column not the whole key thus theres a parital dependency.

SOLUTION

![[Screenshot 2023-11-23 at 8.13.15 AM.png]]


### Third Normal Form

Any non-key field dependent on other non-key field

- should be in 1,2NF
- no Transitive dependency

Example 1 

![[Screenshot 2023-11-23 at 8.16.38 AM.png]]

we can guess value of maxMarks from ExamType
thus MaxMarks transitively depends on ExamType

Solution

![[Screenshot 2023-11-23 at 8.17.57 AM.png]]