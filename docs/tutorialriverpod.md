# Using Riverpod

> If you prefer passing depenendies with Riverpod package, Framy supports it as well!

### A Riverpod usage

Let's say you have a Widget which gets a list of entries from `weightEntries` Provider.
```dart
final weightEntries = Provider((ref) => [ //<--Defined Provider
      WeightEntry(DateTime(2020, 07, 01), 79, ''),
      WeightEntry(DateTime(2020, 07, 02), 78.6, ''),
    ]);

@framyWidget
class HistoryPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Consumer((context, read) {
      final entries = read(weightEntries); //<--Provider usage
      ...
    });
  }
}
```

### Riverpod annotations
If you want to customize the list of entries passed (in other words, change the value of provider), if you need to add 2 annotations.  

#### FramyRegisterRiverpod
First, you have to add `@FramyRegisterRiverpod` annotation above the provider.
```dart
@FramyRegisterRiverpod() //<--- Add this to register Riverpod's Provider
final weightEntries = Provider((ref) => [ 
      WeightEntry(DateTime(2020, 07, 01), 79, ''),
      WeightEntry(DateTime(2020, 07, 02), 78.6, ''),
    ]);
```

#### FramyUseRiverpod
Then wherever you want to customize that provider's value, you need to add `@FramyUseRiverpod` annotation passing the name of the provider.
```dart
@FramyUseRiverpod('weightEntries') //<--- Add this to change provider's value
@framyWidget
class HistoryPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Consumer((context, read) {
      final entries = read(weightEntries);
      ...
    });
  }
}
```

!> Don't forget to annotate your class with FramyModel annotation! Any class you want to customize needs to be annotated with @framyModel.

### Profit 😎
After running the app, your widget will get the provider value which will be overriden with whatever you set up in the generated Framy App.
![Riverpod exanoke](https://user-images.githubusercontent.com/16286046/87152825-b5505a80-c2b6-11ea-8f07-3018922eb7ed.gif)

