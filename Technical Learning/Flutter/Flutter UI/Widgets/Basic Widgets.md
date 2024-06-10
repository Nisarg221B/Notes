next :- [[Widgets 101]]

#flutter 
#flutter-widgets
#flutter-ui 


https://docs.flutter.dev/ui

#### Content
1. Text Widget
2. Row and Column Widget
3. Stack
4. Container


---

### 1. Text

The [Text](https://api.flutter.dev/flutter/widgets/Text-class.html) widget displays a string of text with single style.

The [style](https://api.flutter.dev/flutter/widgets/Text/style.html) argument is optional. When omitted, the text will use the style from the closest enclosing DefaultTextStyle. If the given style's TextStyle.inherit property is true (the default), the given style will be merged with the closest enclosing DefaultTextStyle. This merging behavior is useful, for example, to make the text bold while using the default font family and size.

Using the Text.rich constructor, the text widget can display a paragraph with differently styled TextSpan.

![[Pasted image 20230804114401.png]]
```
const Text.rich(
  TextSpan(
    text: 'Hello', // default text style
    children: <TextSpan>[
      TextSpan(text: ' beautiful ', style: TextStyle(fontStyle: FontStyle.italic)),
      TextSpan(text: 'world', style: TextStyle(fontWeight: FontWeight.bold)),
    ],
  ),
)
```


### 2. Row and Column

These flex widgets let you create flexible layouts in both the horizontal (`Row`) and vertical (`Column`) directions. The design of these objects is based on the web’s flex box layout model.

- Row 

![[Pasted image 20230804154948.png]]

![[Pasted image 20230804154921.png]]

- Items display in a row/column depends on the widget used.
- The items start from the start edge of the main axis.
- The items do not stretch on the main dimension, but can shrink.
- The items will stretch to fill the size of the cross axis.

To cause a child to expand to fill the available horizontal space, wrap the child in an [Expanded](https://api.flutter.dev/flutter/widgets/Expanded-class.html) widget.

The Row widget does not scroll (and in general it is considered an error to have more children in a Row than will fit in the available room). If you have a line of widgets and want them to be able to scroll if there is insufficient room, consider using a ListView.

If you only have one child, then consider using [Align](https://api.flutter.dev/flutter/widgets/Align-class.html) or [Center](https://api.flutter.dev/flutter/widgets/Center-class.html) to position the child.

--- 
In the below code, the row first asks the logo to lay out, and then asks the icon to lay out. The Icon, like the logo, is happy to take on a reasonable size (also 24 pixels, not coincidentally, since both FlutterLogo and Icon honor the ambient IconTheme). This leaves some room left over, and now the row tells the text exactly how wide to be: the exact width of the remaining space. The text, now happy to comply to a reasonable request, wraps the text within that width, and you end up with a paragraph split over several lines.

```

const Row(
  children: <Widget>[
    FlutterLogo(),
    Expanded(
      child: Text("Flutter's hot reload helps you quickly and easily experiment, build UIs, add features, and fix bug faster. Experience sub-second reload times, without losing state, on emulators, simulators, and hardware for iOS and Android."),
    ),
    Icon(Icons.sentiment_very_satisfied),
  ],
)
```
![[Pasted image 20230804155340.png]]
The textDirection property controls the direction that children are rendered in. TextDirection.ltr is the default textDirection of Row children, so the first child is rendered at the start of the Row, to the left, with subsequent children following to the right. If you want to order children in the opposite direction (right to left), then textDirection can be set to TextDirection.rtl.

--- 

The below example divides the available space into three (horizontally), and places text centered in the first two cells and the Flutter logo centered in the third:
```

const Row(
  children: <Widget>[
    Expanded(
      child: Text('Deliver features faster', textAlign: TextAlign.center),
    ),
    Expanded(
      child: Text('Craft beautiful UIs', textAlign: TextAlign.center),
    ),
    Expanded(
      child: FittedBox(
        child: FlutterLogo(),
      ),
    ),
  ],
)
```
![[Pasted image 20230804155514.png]]


Layout for a [Row](https://api.flutter.dev/flutter/widgets/Row-class.html) proceeds in six steps:

1. Layout each child with a null or zero flex factor (e.g., those that are not [Expanded](https://api.flutter.dev/flutter/widgets/Expanded-class.html)) with unbounded horizontal constraints and the incoming vertical constraints. If the [crossAxisAlignment](https://api.flutter.dev/flutter/widgets/Flex/crossAxisAlignment.html) is [CrossAxisAlignment.stretch](https://api.flutter.dev/flutter/rendering/CrossAxisAlignment.html), instead use tight vertical constraints that match the incoming 
2. max height.
3. Divide the remaining horizontal space among the children with non-zero flex factors (e.g., those that are [Expanded](https://api.flutter.dev/flutter/widgets/Expanded-class.html)) according to their flex factor. For example, a child with a flex factor of 2.0 will receive twice the amount of horizontal space as a child with a flex factor of 1.0.
4. Layout each of the remaining children with the same vertical constraints as in step 1, but instead of using unbounded horizontal constraints, use horizontal constraints based on the amount of space allocated in step 2. Children with [Flexible.fit](https://api.flutter.dev/flutter/widgets/Flexible/fit.html) properties that are [FlexFit.tight](https://api.flutter.dev/flutter/rendering/FlexFit.html) are given tight constraints (i.e., forced to fill the allocated space), and children with [Flexible.fit](https://api.flutter.dev/flutter/widgets/Flexible/fit.html) properties that are [FlexFit.loose](https://api.flutter.dev/flutter/rendering/FlexFit.html) are given loose constraints (i.e., not forced to fill the allocated space).
5. The height of the [Row](https://api.flutter.dev/flutter/widgets/Row-class.html) is the maximum height of the children (which will always satisfy the incoming vertical constraints).
6. The width of the [Row](https://api.flutter.dev/flutter/widgets/Row-class.html) is determined by the [mainAxisSize](https://api.flutter.dev/flutter/widgets/Flex/mainAxisSize.html) property. If the [mainAxisSize](https://api.flutter.dev/flutter/widgets/Flex/mainAxisSize.html) property is [MainAxisSize.max](https://api.flutter.dev/flutter/rendering/MainAxisSize.html), then the width of the [Row](https://api.flutter.dev/flutter/widgets/Row-class.html) is the max width of the incoming constraints. If the [mainAxisSize](https://api.flutter.dev/flutter/widgets/Flex/mainAxisSize.html) property is [MainAxisSize.min](https://api.flutter.dev/flutter/rendering/MainAxisSize.html), then the width of the [Row](https://api.flutter.dev/flutter/widgets/Row-class.html) is the sum of widths of the children (subject to the incoming constraints).
7. Determine the position for each child according to the [mainAxisAlignment](https://api.flutter.dev/flutter/widgets/Flex/mainAxisAlignment.html) and the [crossAxisAlignment](https://api.flutter.dev/flutter/widgets/Flex/crossAxisAlignment.html). For example, if the [mainAxisAlignment](https://api.flutter.dev/flutter/widgets/Flex/mainAxisAlignment.html) is [MainAxisAlignment.spaceBetween](https://api.flutter.dev/flutter/rendering/MainAxisAlignment.html), any horizontal space that has not been allocated to children is divided evenly and placed between the children.

- [Column](https://api.flutter.dev/flutter/widgets/Column-class.html), for a vertical equivalent.
- [Flex](https://api.flutter.dev/flutter/widgets/Flex-class.html), if you don't know in advance if you want a horizontal or vertical arrangement.
- [Expanded](https://api.flutter.dev/flutter/widgets/Expanded-class.html), to indicate children that should take all the remaining room.
- [Flexible](https://api.flutter.dev/flutter/widgets/Flexible-class.html), to indicate children that should share the remaining room but that may by sized smaller (leaving some remaining room unused).
- [Spacer](https://api.flutter.dev/flutter/widgets/Spacer-class.html), a widget that takes up space proportional to its flex value.

### 3. Stack

https://api.flutter.dev/flutter/widgets/Stack-class.html

Instead of being linearly oriented (either horizontally or vertically), a `Stack` widget lets you place widgets on top of each other in paint order. You can then use the [`Positioned`](https://api.flutter.dev/flutter/widgets/Positioned-class.html) widget on children of a `Stack` to position them relative to the top, right, bottom, or left edge of the stack. Stacks are based on the web’s absolute positioning layout model.



### 4. Container

The `Container` widget lets you add a visual element to a child widget. Container widgets helps you compose , decorate and position child widgets.
- Use color - to set the background color
![[Screenshot 2023-08-04 at 4.26.11 PM.png|200]]

- Use padding - to add empty space between the child widget and the container boundary.
![[Screenshot 2023-08-04 at 4.26.38 PM.png|200]]

- Use margin - to add empty space that surrounds that widget.
![[Screenshot 2023-08-04 at 4.27.34 PM.png|200]]

- Use Decoration - to add more style to the container - like shape (circle).
![[Screenshot 2023-08-04 at 4.29.27 PM.png|200]]

- Use Alignment property - to align the child within the container.
(once you set the alignment the container will expand to fit its parents width and height)
![[Screenshot 2023-08-04 at 4.30.45 PM.png|200]]
you can over ride this by setting the width and height property
![[Screenshot 2023-08-04 at 4.31.48 PM.png|200]] , ![[Screenshot 2023-08-04 at 4.32.19 PM.png|200]]

or by using the box layout model
![[Screenshot 2023-08-04 at 4.32.59 PM.png|300]] , ![[Screenshot 2023-08-04 at 4.34.29 PM.png|200]]

with box contraints you container can expand to fill a given size. or can apply transforms to your container like rotating 

![[Screenshot 2023-08-04 at 4.35.00 PM.png|300]]. ![[Screenshot 2023-08-04 at 4.35.17 PM.png|200]]



Containers with no children try to be as big as possible unless the incoming constraints are unbounded, in which case they try to be as small as possible. Containers with children size themselves to their children. The `width`, `height`, and [constraints](https://api.flutter.dev/flutter/widgets/Container/constraints.html) arguments to the constructor override this.

Container tries, in order: to honor alignment, to size itself to the child, to honor the width, height, and constraints, to expand to fit the parent, to be as small as possible.

#### Summary (Container)

- Add padding, margins, borders
- Change background color or image
- Contains a single child widget, but that child can be a Row, Column, or even the root of a widget tree