# Using class dependencies

> Framy supports changing complex objects as widget dependencies!

## A widget with custom dependency

Often you will pass more complex dependencies than Strings or integers:
```dart
@framyWidget
class WeatherPreviewCard extends StatelessWidget {
  final WeatherPreview preview;

  const WeatherPreviewCard({this.preview}); //<-- a custom model passed by constructor

  @override
  Widget build(BuildContext context) {
    ....
  }
}
```

## Add framyModel annotation

If you want to customize dependencies passed to the widget, annotate classes with `@framyModel`! 
```dart
@framyModel
class WeatherPreview {
  final int temperature;
  final int feelsLikeTemperature;
  final WeatherCondition condition;

  const WeatherPreview(
    this.temperature,
    this.feelsLikeTemperature,
    this.condition,
  );
}

@framyModel
enum WeatherCondition {
  rainy,
  sunny,
  snowy,
  windy,
}
```

## Run FramyApp

Now generated Framy App will let you customize complex dependencies!

![Custom models example](https://user-images.githubusercontent.com/16286046/87021511-9e860700-c1d5-11ea-8cd4-75fc3c9b337c.gif)
> Framy will generate a panel with dependencies passed by constructor!