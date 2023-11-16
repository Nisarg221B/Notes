
#flutter_inherited_widgets
#flutter-ui 
#flutter-theme 

## Inherited widgets

![[Screenshot 2023-08-07 at 4.00.31 PM.png|400]]

what if we have a data, service or asset which we need to access from a bottom of the widget tree , we have to pass all those values in the constructors of the widgets to pass it down.

this can be solved by the inherited widget
- When you put it in your tree , you can get a reference to it from any widget below it in the tree.
![[Screenshot 2023-08-07 at 4.01.54 PM.png|400]]


lets say theres an image asset in the inherited widget "InheritedNose"- 
![[Screenshot 2023-08-07 at 4.03.35 PM.png]]

Now any descendent like Filipwidget  of our inherited nose get access to it in its build method by calling context.inheritFromWidgetOfExactType('Type of your custom inherited widget').
[see about BuildContext](https://www.educative.io/answers/what-is-buildcontext-in-flutter)

![[Screenshot 2023-08-07 at 4.03.15 PM.png]]

to make this more simpler, Inherited widgets often include the static method 'of' , which calls the inheritFromWidgetOfExactType for you. as you can see above 

![[Screenshot 2023-08-07 at 4.07.09 PM.png|500]]

way to get a global theme of a material app you do
```
Theme.of(context).primaryColor 
```
therefore theme is a type of inherited widget.



