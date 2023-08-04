
#dart 
#Sound-null-safety 

```
bool isEmpty(String string) => string.length == 0;

main() {
isEmpty(null);
}
```

If you run this Dart program without null safety, it throws a NoSuchMethodError
exception on the call to .length. The null value is an instance of the Null class,
and Null has no “length” getter. Runtime failures suck. This is especially true
in a language like Dart that is designed to run on an end-user’s device. If a server
application fails, you can often restart it before anyone notices.

But when a Flutter app crashes on a user’s phone, they are not happy.
When your users aren’t happy, you aren’t happy.

__SOUND NULL SAFETY

SOUND - if type system determines that something is not null , then that thing can never be null
NULL SAFETY - Not having null values where you don't expect them.

“Soundness” in the context of static checking means different things to different people.
For us, in the context of null safety, that means that if an expression has a static type
that does not permit null, then no possible execution of that expression can ever evaluate to null.
The language provides this guarantee mostly through static checks, but there can be
some runtime checks involved too.(any place where those runtime checks happen will be your choice.)

---


## Nullability in the type system

null is an instance of Null class thus before null safety, the static type system allowed the value `null`
to flow into expressions of any of those types.

In type theory lingo, the `Null` type was treated as a subtype of all types:

![[Pasted image 20230725184710.png|400]]

The set of operations—getters, setters, methods, and operators—allowed on some expressions are defined by its type. If the type is `List`, you can call `.add()` or `[]` on it. If it’s `int`, you can call `+`. But the `null` value doesn’t define any of those methods. Allowing `null` to flow into an expression of some other type means any of those operations can fail. This is really the crux of null reference errors—every failure comes from trying to look up a method or property on `null` that it doesn’t have


### Non-nullable and nullable types
https://dart.dev/null-safety/understanding-null-safety#using-nullable-types

Null safety eliminates that problem at the root by changing the type hierarchy. The `Null` type still exists, but it’s no longer a subtype of all types. Instead, the type hierarchy looks like this:

![[Pasted image 20230725184905.png|400]]

Since `Null` is no longer a subtype, no type except the special `Null` class permits the value `null`. We’ve made all types _non-nullable by default_. If you have a variable of type `String`, it will always contain _a string_. There, we’ve fixed all null reference errors.

![[Pasted image 20230725191133.png|200]]

If you have an expression with a nullable type, what can you do with the result? Since our principle is safe by default, the answer is not much. We can’t let you call methods of the underlying type on it because those might fail if the value is `null`:
```
// Hypothetical unsound null safety:
bad(String? maybeString) {
  print(maybeString.length);
}

main() {
  bad(null);
}
```

This would crash if we let you run it. **The only methods and properties we can safely let you access are ones defined by both the underlying type and the `Null` class. That’s just `toString()`, `==`, and `hashCode`. So you can use nullable types as map keys, store them in sets, compare them to other values, and use them in string interpolation, but that’s about it.**




## Implicit Downcast


Implicit Downcast where for example if an Object instance (x) is passed to where the complier expects a String instance , the object is implicitly downcasted to String ( x as String ).

So in case of null , the nullable types (String?) are superclass of the conresponding type and Null class ( String | Null ), letting the complier do the implicit downcast would result in unsafe code as if the String? is null , the null would flow in and that could fail.

```
requireStringNotNull(String definitelyString) {
  print(definitelyString.length);
}

requireStringNotObject(String definitelyString) {
  print(definitelyString.length);
}

main() {
  // this is not ok
  String? maybeString = null; // Or not!
  requireStringNotNull(maybeString);

  // This is ok
  Object maybeString = 'it is';
  requireStringNotObject(maybeString); // downcasted to string (maybeString as String)
  
  // But this is not
  Object? maybeString = 'it is'; // Object? -> String? -> null
  requireStringNotObject(maybeString); // downcasted to string but not safe , might     // give runtime error 
}
```

##### Thus to avoid all this , the implicit downcast was removed completely

```
// Using null safety:
requireStringNotObject(String definitelyString) {
  print(definitelyString.length);
}

main() {
  Object maybeString = 'it is';
  requireStringNotObject(maybeString as String); // only explicit downcast allowed.
}
```

![[Pasted image 20230725190939.png]]

There is a region of non-nullable types. Those types let you access all of the interesting methods, but can never ever contain `null`. And then there is a parallel family of all of the corresponding nullable types. Those permit `null`, but you can’t do much with them. We let values flow from the non-nullable side to the nullable side because doing so is safe, but not the other direction.



### Never Type

Since `Object` is non-nullable now, it is no longer a top type. `Null` is not a subtype of it. Dart has no _named_ top type. If you need a top type, you want `Object?`. Likewise, `Null` is no longer the bottom type. If it was, everything would still be nullable. Instead, we’ve added a new bottom type named `Never`:

![[Pasted image 20230725192948.png|400]]

![[Screenshot 2023-07-25 at 7.31.45 PM.png]]
The new bottom type `Never` has no values. (What kind of value is simultaneously a `String`, `bool`, and `int`?) So what does it mean for an expression to have type `Never`? It means that expression can never successfully finish evaluating. It must throw an exception, abort, or otherwise ensure that the surrounding code expecting the result of the expression never runs.


### summary
see null_safety.dart  in language learning section for better understanding the below points.

![[Screenshot 2023-07-26 at 1.25.44 AM.png]]
![[Screenshot 2023-07-26 at 1.27.06 AM.png]]

![[Screenshot 2023-07-26 at 1.28.14 AM.png]]
