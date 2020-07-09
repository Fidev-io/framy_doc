# Adding own widgets

> Framy lets you annotate your widgets to see them in isolation!

## Add framyWidget annotation

All you have to do is adding `framyWidget` annotation to your widget class! 
```dart
@FramyWidget() //<-- Add this!
class CounterTitle extends StatelessWidget {
  final String verb;
  final int counter;

  const CounterTitle({Key key, this.verb = 'pushed', this.counter = 0})
      : super(key: key);
  @override
  Widget build(BuildContext context) {
    return Column(
      key: Key('Counter title'),
      mainAxisAlignment: MainAxisAlignment.center,
      children: <Widget>[
        Text(
          'You have $verb the button this many times:',
        ),
        Text(
          '$counter',
          style: Theme.of(context).textTheme.headline4,
        ),
      ],
    );
  }
}
```

## Run FramyApp

Now you can run `main.app.framy.dart` to see your widget in isolation!
![FramyApp widget example](https://user-images.githubusercontent.com/16286046/87019492-f8d19880-c1d2-11ea-8751-d15a66ae0c2f.gif)

> Framy will generate a panel with dependencies passed by constructor!