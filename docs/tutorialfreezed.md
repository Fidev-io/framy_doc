# Using Freezed

> Framy provides support for models generated with Freezed package out of the box!

## Add framyModel annotation

Annotating models using Freezed works without any extra actions, just add `@framyModel` annotation to the main class
```dart
@framyModel
@freezed
abstract class StatisticsPageState with _$StatisticsPageState {
  const factory StatisticsPageState.loaded(List<WeightEntry> weightEntries) =
      Loaded;

  const factory StatisticsPageState.loading() = Loading;

  const factory StatisticsPageState.error([String message]) = Error;
}
```

## Use constructor dropdown

Framy will generate constructor dropdown to let you choose which type of your Freezed class you want to pass.
![Freezed example](https://user-images.githubusercontent.com/16286046/87018461-8f04bf00-c1d1-11ea-9e57-bd3347bbcf9a.gif)