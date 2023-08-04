#dart 

---
prev :- [[Intro]]
next :- [[Dart VM]]

---

### Topics covered

1. #Dart-VM
2. #JIT-Compiler-dart
3. #AOT-Compiler-dart
4. #Flutter-dart

---
### 1. Dart-VM

Dart converts the source code into intermediate language or machine code specific to platform so that the code can run on that dart virtual machine on that platform.

- **Native platform**: For apps targeting mobile and desktop devices, Dart includes both a Dart VM with just-in-time (JIT) compilation and an ahead-of-time (AOT) compiler for producing machine code.
    
- **Web platform**: For apps targeting the web, Dart can compile for development or production purposes. Its web compiler translates Dart into JavaScript.

![[Screenshot 2023-07-24 at 8.33.08 AM.png|400]]



![[Screenshot 2023-07-24 at 8.32.27 AM.png]]



### 2. Development phase

During the development phase its better to have a language which supports the below feature :

![[Screenshot 2023-07-24 at 8.22.50 AM.png| 300]]

To provide the above functionality the dart language has JIT Compiler which compiles the code ite needs and when it needs.
![[Screenshot 2023-07-24 at 8.24.00 AM.png|300]]

![[Screenshot 2023-07-24 at 8.24.28 AM.png]]

JIT compiler is not the best , nor the most optimal compiler for the production phase as :

1. JIT does not transform the Dart Code into Machine Code , but rather into an intermediary language (for faster development cycle )
2. Into Production phase , the users doesn't care about the JIT features like fast testing, debugging or hot-reload. all he cares about is for the app to start and run as fast as it can on his device. the only way an app or program run really fast by compiling source code into native machine code(which is done by AOT compiler).


### 3. Production phase

![[Screenshot 2023-07-24 at 8.29.11 AM.png|300]]

![[Screenshot 2023-07-24 at 8.29.35 AM.png|300]]

![[Screenshot 2023-07-24 at 8.29.57 AM.png]]

### For world wide web


![[Screenshot 2023-07-24 at 8.31.05 AM.png | 400]]

### 4. Flutter

The [Flutter framework](https://flutter.dev/) is a popular, multi-platform UI toolkit that’s powered by the Dart platform, and that provides tooling and UI libraries to build UI experiences that run on iOS, Android, macOS, Windows, Linux, and the web.

