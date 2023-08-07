#flutter-ui 
#flutter-expanded

Widgets get sized based **on their size preferences** and **parent widget size constraints.**

![[screenshot-www.udemy.com-2023.08.07-20_19_30.png]]

The constraints of the parent widget overrides the preferences of the child widget.

![[screenshot-www.udemy.com-2023.08.07-20_21_59.png]]

In a case like above where both the child and parent are unconstrained on any of the axis , it causes problem as flutter will not be able to fix anything to show.

Thus in such a scenario we can wrap the child widget with a expanded widget constraints the child widget to take only the actually available size instead of getting as much size as possible ( infinity ).


