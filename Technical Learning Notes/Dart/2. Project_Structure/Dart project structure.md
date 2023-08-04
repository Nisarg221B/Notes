
#dart_project_structure
#dart 
next :- [[All kinds of packages]]

---

![[Screenshot 2023-07-24 at 12.02.11 PM.png]]

### Dart Packages

There is nothings as a dart project , its always a dart package. which can depend on other dart packages.
**what is a dart package ?** 

**pub.dev** platform contains all the published dart packages

Dart packages can be imported to your package for various utilities as listed below:

![[Screenshot 2023-07-24 at 12.12.28 PM.png|400]]

A. Local project/Package
B. HTTP package
C. Json Serialisable package
D. hive package 


![[Screenshot 2023-07-24 at 12.14.00 PM.png|400]]

Thus there are two kinds of package : 

![[Screenshot 2023-07-24 at 12.15.04 PM.png|400]]

### so there has to be a package manager who handles the package what it depends on and their dependencies and so on.


### pub package manager
1. pubspec.yaml ( where we state the external dependency packages of our local package , name of our package and on which dart version our package works on)
2. pubspec.lock ( auto generated when we run "dart pub get" which also get run automatically when we mention the external package in pubspec.yaml )
3. package_config.json - contains paths and settings of downloaded packages.

### So the question is how do the developers expose their work from inside their packages - Through Libraries!

![[Screenshot 2023-07-24 at 12.22.11 PM.png|400]]




## Pubspec.yaml file  syntax and options
#pubspec-yaml

For a directory to be called a dart package it must have at least a pubspec.yaml file in it.

![[Screenshot 2023-07-24 at 3.11.01 PM.png]]


### Types of Dependencies 

![[Screenshot 2023-07-24 at 3.13.04 PM.png]]


![[Screenshot 2023-07-24 at 3.13.24 PM.png]]

,Therefor the test package is dev-dependencies


## See if the dependency will work or not based on dart version.

![[Screenshot 2023-07-24 at 3.15.28 PM.png]]![[Screenshot 2023-07-24 at 3.16.32 PM.png]]



### analysis_options.yaml
#analysis_optoins_dart

![[Screenshot 2023-07-24 at 5.52.43 PM.png]]



