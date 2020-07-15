# Device Preview

> You can use Device Preview to have full insight on how your widgets will behave!

## Add dependency to pubspec.yaml

First, you need to add `device_preview` dependency to your `pubspec.yaml` file.
Get the latest version from the package site: [https://pub.dev/packages/device_preview](https://pub.dev/packages/device_preview)
```yaml
# Replace any's with the latest versions
dependencies:
  framy_annotation: any
  device_preview: any #<-- Add device_preview

dev_dependencies:
  build_runner: any
  framy_generator: any
```

## Update FramyApp annotation

We also need to tell Framy that we want to use device preview by adding `useDevicePreview: true` to FramyApp annotation.

```dart
@FramyApp(useDevicePreview: true)  //<-- Add this
class WeightTrackerApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: AppTheme.themeData,
      home: HomePage(),
    );
  }
}
```

## Use the device preview
After restarting the application, you can use device preview to have full control on how your widgets are presented!
![Device preview example](https://user-images.githubusercontent.com/16286046/87018103-156cd100-c1d1-11ea-8b6b-c4be193460e5.gif)
