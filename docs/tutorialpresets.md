# Defining presets

> If you don't want to manually set up dependencies, you can do it using Presets!

## A widget with custom dependency

Assuming your widget is being passed an object in constructor:
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

## Create a preset method

Create a method(s) that will return an object of the same type as the dependency:
```dart
WeatherPreview sunnyDay() => WeatherPreview(39, 40, WeatherCondition.sunny);

WeatherPreview rainyAndCold() => WeatherPreview(3, -1, WeatherCondition.rainy);
```

## Add framyPreset annotation

Add framyPreset annotation to every preset method:
```dart
@framyPreset //<-- Add this annotation
WeatherPreview sunnyDay() => WeatherPreview(39, 40, WeatherCondition.sunny);

@framyPreset //<-- Add this annotation
WeatherPreview rainyAndCold() => WeatherPreview(3, -1, WeatherCondition.rainy);
```

## Run FramyApp

Now you can select defined presets in a dropdown!

![Presets example)](https://user-images.githubusercontent.com/16286046/87023674-587e7280-c1d8-11ea-854f-805616b67aef.gif)