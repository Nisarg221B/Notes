
### Particularities of Dart

#dart

next :- [[The Platforms]]

---

Topics covered

1. #Type-safe-language
2. #Static-Analyzer and #runtime-check
3. #dynamic-type
4. #var-keyword
5. #Sound-null-safety
---

1. Dart is type safe language - The only operations that can be performed on
    data in language are those allowed by the type of the data.
  

 2. Sound type system - dart won't allow the system to be in unknown state.

		a. static type check ( compile time ) - local check , compilation fails
		b. runtime check - aditional check when the program runs , runtime exceptions

```
int x;
x.toUpperCase(); // not allowed - compilation fails
string y;
y = 3 // not allowed
```

3. Dynamic typing

** dynamic ( it is a type )**
To get around the above restriction the developer can use dynamic type,
which allows him to bypass the static type check at compilation time.

in such case dart will dynamically infer the variable b type at runtime.

```
dynamic b = 3.4;
b.aRandomMethod(); // <- no compilation error , will cause runtime exception
```


4. Var keyword

Types are mandatory but don't have to be annotated because dart can infer types
by using the var keyword at compile type.

** var (it is not a type , its just a keyword which helps to assign a type ) **

var x = 5.4; // the datatype of x will be inferred to double right away to compile time.

  
```
void main_dynamic {

	dynamic a = 5;
	print(a.runtimeType); // int
	a = 7.0;
	print(a.runtimeType); // double
	a = 'test';
	print(a.runtimeType); // String
}

```

  
```

void main_static {

	var a; // if not assigned to any value it will set the type of a to dynamic;
	// = dynamic a
	
	var b = 5;
	print(b.runtimeType); // ?int (static check)
	b = 7.0; // error
	b = 'test'; // error
	print(b.runtimeType);
}

```
  
5. Sound Null Safety - Variables can't contain null , unless you say they can

This means values can’t be null unless you say they can be. With sound null safety, Dart can protect you from null exceptions at runtime through static code analysis. Unlike many other null-safe languages, when Dart determines that a variable is non-nullable, that variable can never be null. If you inspect your running code in the debugger, you see that non-nullability is retained at runtime; hence _sound_ null safety.