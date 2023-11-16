
[reference video](https://www.youtube.com/watch?v=wE7khGHVkYY)

#flutter_stateless_widget
#widget 


Widgets are really just configurations for pieces of an apps UI , they are blue prints.

so what are they configurations for ? - Elements

An element is an widget thats been made real and mounted on screen, and its the element tree that represents what's actually displaying on your device at any given moment.

Each widget class has both a corresponding element class and a method to create an instance.
- Stateless widget for example creates a stateless element, that createElement method gets called when the widget is mounted to the tree. the createElement provides the Element which is mounted to the element tree with a reference to the widget that created it.
```
@override
StatelessElement createElement() => new StatelessElement(this);
```
![[Screenshot 2023-08-01 at 10.52.32 AM.png|400]]

- Stateless element than asks if it should have any children and calls the widgets build method to check.

![[Screenshot 2023-08-01 at 10.54.39 AM.png|400]]

- This child widgets than creates their own elements and are mounted on the element tree as well.
![[Screenshot 2023-08-01 at 10.55.29 AM.png|400]]

- so the app has two trees , one that represents what's actually on the screen and one that holds the blueprints they were made from , the widgets.
### So what starts the whole process

![[Screenshot 2023-08-01 at 10.59.13 AM.png|500]]

The DogApp class which represents the entire app is itself a StatelessWidget.
In the main() theres a runApp method and thats the starting point

- The RunnApp takes a widget and mounts it as the root element for the app with the height and width constraints that match the size of the screen.

![[Screenshot 2023-08-01 at 11.02.05 AM.png|400]]

