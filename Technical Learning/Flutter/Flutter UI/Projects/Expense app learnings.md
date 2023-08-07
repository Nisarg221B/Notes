#flutter 
#flutter-ui 
#flutter-widgets 

---
- adaptive designing 


----
#flutter-theme

- Theme
	- ColorScheme 
		- ColorScheme kColorScheme =
		 ColorScheme.fromSeed(seedColor: const Color.fromARGB(255, 10, 0, 0))
		// generating a ColorScheme from a Seed color
		// now we can use kColorScheme and the flutter will adjust theme of all elements by itself or you can adjust by yourself in themeData.copyWith() constructor 
		by setting the values to
			- kDarkColorScheme.secondaryContainer
			- kDarkColorScheme.onSecondaryContainer
			- kDarkColorScheme.onPrimaryContainer
			- kDarkColorScheme.primaryContainer

			
	- ThemeDate.copyWith()
		- useMaterial3 - true
		- colorScheme // set your colorScheme
		- appBarTheme().copyWith()
						- backgroundColor: kColorScheme.onPrimaryContainer
						- foregroundColor: kColorScheme.primaryContainer
		- textTheme().copyWith()

you can use the above setted themes directly in the style options of widgets as show below

style: Theme.of(context).textTheme.titleMedium

----
#flutter-ListView
#flutter-ScaffolMessanger

- ListView
			- ListView.builder()
					- itemCount
					- itemBuilder
						- key - ValueKey()
					- onDismissed
					- child
- ScaffoldMessanger 
			- showSnackBar
			- clearSnackBar

---

#flutter-overlays

- Overlay 
			-  showModalBottomSheet
					- context
					- builder	
			- showDialog
					- context
					- builder : (ctx) => AlertDialog
													- title
													- content
													- actions

- Navigator.pop(context)

--- 
#flutter-TextField

- TextField 
		- controller
		- onChange
		- maxLength
		- keyboardType
		- Decorations
				- label
				- prefix
- TextEditingController()
		( TextEditingController x = TextEditingController() )
		-  x.text (access its value)
- Dispose() 

--- 
#flutter_DatePicker

- DatePicker 
	- showDatePicker     // returns a future
		- context
		- initialDate
		- firstDate
		- lastDate

---
#flutter_DropDown

- Dropdown

```

	 - DropdownButton2 (third party widget)
		- dropdownDecoration
		- value // placeholder value
		- items  // list of DropdownMenuItem
				- <list>DropDownMenuItem
				- value  //  value to return if the user selects this menu item
				   //  Eventually returns on the call to DropDownMenu.onChanged
				- child  // creates an item for dropdown menu
		- onChanged // is called when the user selects an item
				- (value){}

```

---
#flutter-AppBar

- AppBar()
		- title
		- actions (list of buttons)

- Spacer()
-  IconButton
- double.trypass()