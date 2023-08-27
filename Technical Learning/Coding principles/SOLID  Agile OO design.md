

## Introduction

- good code is perfectly obvious
	- If you modify something and it breaks its a bad code.

- **Rigid code** is a code that has dependencies that snake out in so many directions that you cannot make an isolated change without changing everything else around it.( bad dependencies, systems that are coupled )

another symptom of bad code similar to that one is called fragility

- **Fragility** is the tendency of the code to break in many places even when you only
change it in one place. you make one very simple change and a whole bunch of other things break but they break in parts of the codes that have no relationship to what you changed. 


The common thread here is coupling dependency. 

## OO




## Class Design Principles

#### SRP: The Single Responsibility Principle

A class should have one and only one, reason to change

![[Screenshot 2023-08-27 at 4.44.39 PM.png|400]]

How many changes could be requested in the above system? from how many sources could they come ? 

if there was problem with CalcPay function  - CFO
if there were a bug in ReportHours - CEO
if there were problem with WirteEmployee which leads to crashing of database and loss of data - CTO 

so this class Employee has three responsibilities or three reason to change. it has responsibilities to three different actors or organisations all at the same time.

so basically don't put the functions which change for different reasons in the same class.

a possible solution:-
![[Screenshot 2023-08-27 at 4.52.18 PM.png|400]]

#### OCP: The Open/Closed Principle

A class or Modules should be open for extension but closed for modification.







#### LSP: The Liskov Substitution Principle
#### ISP: The Interface Segregation Principle

#### DIP: The Dependency Inversion Principle







