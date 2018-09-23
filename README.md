# Nested Navigation Demo Adjustment
This repository is an adjustment to bizz84s nested-navigation-demo.
You'll find it [here](https://github.com/bizz84/nested-navigation-demo-flutter)

## About bizz84s version
This architecture is very good to have a BottomNavigationBar where the states of each Tab is saved but there is a big porblem if you want to add a TextInput to a Tab. You can't focus it properly and the keyboard will not open. This is because the navigators are on the same level and the focus is everytime at the last navigator even the offstage property is on true. More Informations: [#17096](https://github.com/flutter/flutter/issues/17098)

## Solution
My Solution for this Problem is to use the root navigator to navigate to the page within a TextInput.

Just push the context of your Material App to the pages and 
```dart
Navigator.of(rootContext).pushNamed('/inputPage');
```
