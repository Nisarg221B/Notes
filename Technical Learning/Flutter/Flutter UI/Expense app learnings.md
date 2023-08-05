
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


----
- ListView
			- ListView.builder()
					- itemCount
					- itemBuilder
						- key
					- onDismissed
					- child
- ScaffoldMessanger 
			- showSnackBar
			- clearSnackBar
- Key
---
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

- context
--- 
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
- DatePicker 
	- showDatePicker     // returns a future
		- context
		- initialDate
		- firstDate
		- lastDate

---
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

- AppBar()
		- title
		- actions (list of buttons)

- Spacer()
-  IconButton
- double.trypass()