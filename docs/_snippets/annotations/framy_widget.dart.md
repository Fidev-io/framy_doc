```dart
@FramyWidget()
class CounterTitle extends StatelessWidget {
  final String verb;
  final int counter;

  const CounterTitle({this.verb = 'pushed', this.counter = 0});

  @override
  Widget build(BuildContext context) {
    return Column(
      key: Key('Counter title'),
      mainAxisAlignment: MainAxisAlignment.center,
      children: <Widget>[
        Text('You have $verb the button this many times:'),
        Text('$counter', style: Theme.of(context).textTheme.headline4),
      ],
    );
  }
}
```