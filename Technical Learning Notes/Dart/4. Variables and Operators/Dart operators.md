#dart 
#dart-operators
#dart_type_test_operatos



1. == operator and identical() function
 Both of them check the hashcode of the objects being compared
 
 therefore 
 ```
 int a = 4;
 int b = 4;
 List<int>c = [1,3,4,5];
 List<int>d = [1,3,4,5];
 List<int>e = const [1,2,5,4];
 List<int>f = const [1,2,5,4];

 print(a == b); // true
 print(c == d); // false
 print(d == e); // false
 print(e == f); // true

 identical(a,b); // true;
 identical(d,e); // false;

 // " == and identical does the same thing "
 // though == can be useful when there is a need to overload == operator for a specific class

```


3. Type Test Operators

![[Screenshot 2023-07-27 at 11.45.09 AM.png]]


4. BIT operators
![[Screenshot 2023-07-27 at 11.51.59 AM.png|300]]

5. Logical operators - && , ||

6. Assigment operators

![[Screenshot 2023-07-27 at 11.53.40 AM.png]]

??=  (assign value to a variable only if that variable has not been assigned yet)

int? a = 7;
a ??= 5; // warning and 'a' will not be assigned to 5 , and the value will remain 7

