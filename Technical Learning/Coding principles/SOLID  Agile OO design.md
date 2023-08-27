

https://www.youtube.com/watch?v=zHiWqnTWsn4

## Introduction

- good code is perfectly obvious
	- If you modify something and it breaks its a bad code.

- **Rigid code** is a code that has dependencies that snake out in so many directions that you cannot make an isolated change without changing everything else around it.( bad dependencies, systems that are coupled )

another symptom of bad code similar to that one is called fragility

- **Fragility** is the tendency of the code to break in many places even when you only
change it in one place. you make one very simple change and a whole bunch of other things break but they break in parts of the codes that have no relationship to what you changed. 


The common thread here is coupling dependency. 

## OO

![[Screenshot 2023-08-27 at 7.01.29 PM.png|500]]

when theres a dependency tree like above where the high level modules depends on low level module and should also know low level details , if theres a change need to be made or a bug in any low level module , because of high coupling it causes the refactoring of all the high level files in the system thus changing the high level policy.


What is object oriented design ?

- Encapsulation 

We had perfect encapsulation in C with separate headers and c files , where the users were only presented with just the function signatures a perfect encapsulation and then C++ came along with objects and added variables to the header files now all of a sudden all variables were visible in the header files to the users.

to evade that we introduced hacky keywords thus OO languages weekend the encapsulation with hacky keywords of public private protected and no names apparently. 

- Inheritance

C++ did make the inheritance better than c , best part of C++ was multiple inheritance and thus java took it away they were too lazy too deal with diamond problem of multiple inheritance and so they invented some horrible act called interface  and they stuck back that in the language instead. interface is nothing but an abstract class with a bunch of abstract methods its not a special thing , the only this special about interface in java is what you can't do to it , you can't inherit multiple classes but the only thing you're allowed to inherit multiply is interfaces (a lazy hack).


- Polymorphism 

Polymorphism is intersting 

![[Screenshot 2023-08-27 at 7.31.17 PM.png]]

here the flow of control goes from M to N . with M calling function f in N, 

but if I have Polymorphism what we can do is put interface in between them and define function f in it. The M module can mention the name of that interface and use it to call F , the N module will derive from that interface. 

Now in this case the compile time dependency - it points against the flow of control.

![[Screenshot 2023-08-27 at 7.35.00 PM.png]]

This is what polymorphism gives you , the ability to create one module calling another and yet have the compile time dependency point against the flow of control.

and if you have that power you suddenly have absolute control over your dependency structure thus you can avoid writing fragile rigid and non reusable modules you can go around what goes wrong with software by carefully deciding which direction the arrows between modules should point. Thats what OO is. 

OO is about managing dependencies by selectively inverting certain key dependencies in your architecture so that you can prevent rigidity , fragility , non reusability.


## Class Design Principles

#### 1. SRP: The Single Responsibility Principle

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

#### 2. OCP: The Open/Closed Principle

A class or Modules should be open for extension but closed for modification.


not the OO approach : 

![[Screenshot 2023-08-27 at 6.44.12 PM.png|600]]

In the above if we needed to add a over we need to re-compile and refactor almost every file in the above module. 

Whereas the below code uses OO in a efficient manner , where if we needed to add a oval , we just need to add file with that class essentially just extending the module.

![[Screenshot 2023-08-27 at 6.46.11 PM.png|600]]

the flow of control works the same way , but at the compile time the above high level policy do not know about the low level details.

#### 3. LSP: The Liskov Substitution Principle

"Derived classes must be usable through the base class interface, without the need for the user to know the difference"

![[Screenshot 2023-08-27 at 6.52.33 PM.png|400]]

We have a Rectangle and a new requirement has come along for a Square.

so Square inherits from Rectangle makes perfect sense. and as memory is cheap we will override setWidth and setHeight.

![[Screenshot 2023-08-27 at 7.44.52 PM.png|500]]

A class square is not a square , a class square represents a square and similarly a class rectangle represents a rectangle but the representatives of the things do not share the relationship things they represent.

thus rectangle is not parent of square they got nothing in common they got different number of variables they don't have same behaviour.

this is a violation of liskov substitution because square is not substitutable for rectangle. 

Inheritance is not an "is a" relationship, inheritance is really just the redeclaration of functions and variables in the sub-scope. 


#### 4. ISP: The Interface Segregation Principle

#### 5. DIP: The Dependency Inversion Principle







