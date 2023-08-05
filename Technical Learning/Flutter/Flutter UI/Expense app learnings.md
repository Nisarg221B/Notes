
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