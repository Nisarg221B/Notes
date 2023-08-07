
#flutter 
#flutter-widgets 
#flutter-statefull-widgets


----

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

![[Screenshot 2023-08-07 at 3.12.12 PM.png]]

When flutter asks the statefull widget it create an element it returns a 'stateful element'

![[Screenshot 2023-08-07 at 3.13.13 PM.png|400 ]]

these stateful element than calls createState method (or in other terms "asks the stateful widget to make a state object "). now this createState method creates a state object and stateful element holds onto it.

![[Screenshot 2023-08-07 at 3.18.06 PM.png|500]]

now its time to build child widgets therefore stateful element calls the state objects build method. as the state object references the widget it can use its values to construct the child widget which are stateless widgets which in turns creates a stateless element which gets mounted on the tree.

![[Screenshot 2023-08-07 at 3.22.18 PM.png|600]]

Now if we add setState in the State object to increase the count.
setState triggers update on UI

![[Screenshot 2023-08-07 at 3.23.10 PM.png|400]]

when setState runs, it increases the count and marks its object dirty meaning - it will build its children on next frame. so when the next frame goes around the stateful element calls build method in the state object to rebuild the children  

![[Screenshot 2023-08-07 at 3.27.58 PM.png|500]]

The old object Text(tom:0) goes away and in comes the new one.

![[Screenshot 2023-08-07 at 3.28.43 PM.png|500]]

and as the new widget is same as the old one they are both Text , the stateless element stays where it is and just update itself to reference the new widget. ( #flutter-keys ).


The State Objects has long lifespans they stay attached to the element tree even when the original widget gets replaced by a new one as long as that new one is of the same type.

for example if the original item counter widget is to changed itself , may be because of the change above it in the tree. ( side note: here the "didUpdateWidget" method can be overriden to know if the state objects widget (itemCounter) gets replaced ).

![[Screenshot 2023-08-07 at 3.32.07 PM.png|500]]

![[Screenshot 2023-08-07 at 3.35.19 PM.png|500]]

the original widget gets replaced, though as the new widget is the same type of widget as the old one, the stateful element and the state object stay where they are , they survive the change in the widget and mark themself as dirty so that their childrens get rebuild. 

so in the next frame
-> **state objects build method kicks out a text widget with "its count value" but with the "new itemcounter widgets name value". <-

thus Text(Dan : 1), and the stateless element of the text stays where it was.

![[Screenshot 2023-08-07 at 3.38.41 PM.png|500]]





