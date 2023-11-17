#flutter 
#flutter-riverpod
#flutter-statemanagement

There are three types of providers
- Provider - (provides immutable values - read only widget)
- StateProvider - (upgrade over Provider - uses notifier to control state )
- StateNotifier and StateNotifierProvider

#### Provider
```dart
Provider<List<Meal>> mealsProvider = Provider((ref) => dummyMeals);
// or
final nameProvider = Provider<String>((ref)=> 'nisarg');
```

ref- provider ref allows us to communicate between one provider to other.

You can read this provider in any file using below methods

a. Using ConsumerWidget instead of statelessWidget
	and adding *WidgetRef ref* as extra argument in build method
	this widget ref allows us to communicate from a widget to other providers

- in case of stateful widget just replace 
	- StatefulWidget - ConsumerStatefulWidget
	- state - ConsumerState
	- in this case we get a ref variable directly from ConsumerState so no need to add it as a argument in build method.

```dart
	final name = ref.watch(nameProvider); // listen to the name provider
	final nameRead = ref.read(nameProvider); // ref.read is just a one time read and do not listen for the changes.
```
- it is recommended to use ref.watch inside the build method
- and ref.read in other functions

b. wrapping the widget tree with consumer

```dart
body: Consumer(builder: (context,ref,child){
	final name = ref.watch(nameProvider);
	return Column(
		children:[
			Center(
				child: Text(name),
			),
		],
	);
})
```

### StateProvider

```dart
final nameProvider = StateProvider<String?>((ref)=> null);
```

you can read it same as above

```dart
final name = ref.watch(nameProvider) ?? '';
```

To update the value of StateProvider 

can convert the ProviderState to StateController using .notifier and then access the update method of the provider

```dart
ref.read(nameProvider.notifier).update((state)=>value);
```

- it is used for very simple values like string, int, double, boolean etc but it gets difficult for complex values like inside of a class or map.

