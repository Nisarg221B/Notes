

- **Stateless Widget** - immutable configurations or blueprints for an element.
- **Statefull Widget**  - It provides immutable configuration info and a state object that can change over time and trigger rebuilds of the UI.

Every Flutter Widget has a built-in **lifecycle**: A collection of methods that are **automatically executed** by Flutter (at certain points of time).

There are **three** extremely important (stateful) widget lifecycle methods you should be aware of:

- `initState()`: Executed by Flutter when the StatefulWidget's State object is **initialized**    
- `build()`: Executed by Flutter when the Widget is built for the **first time** AND after `setState()` was called
- `dispose()`: Executed by Flutter right before the Widget will be **deleted** (e.g., because it was displayed conditionally)


### Stateful Widget Lifecycle
 
![[Screenshot 2023-08-07 at 11.17.17 AM.png|400]]

#### Important ones 

![[Screenshot 2023-08-07 at 12.39.13 PM.png|400]]

see the project_4 numberwidget file of the flutter learning  for better understanding.

createState() -> 
first method which is called in Statefulwidget lifecycle and then our lifecycle begins

initState() ->
In the beginning of our lifecycle initstate method is called this method is called every time when the state is created here we can initialise our widget

build()->
then comes our build method which creates our UI

SetState()->
Whenever the SetState method is called flutter builds the ui again , therefore the build() method of that widget is called

didUpdateWidget()->
this method is called whenever the configuration of the whole widget changes, implies the stateful widget constructor function is called with different configuration, this will call the didUpdateWidget method  which then calls the build method if necessary.

Dispose()->
and at the end of our life cycle dispose method is called

<iframe width="700" height="400" src="https://www.youtube.com/embed/AqCMFXEmf3w?list=PLOU2XLYxmsIJyiwUPCou_OVTpRIn_8UMd" title="How Stateful Widgets Are Used Best - Flutter Widgets 101 Ep. 2" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Lets consider a StatefullWidget ItemCounter(String name)

