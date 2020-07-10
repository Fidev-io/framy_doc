# Annotations

Framy Annotations package offers a variety of annotations to generate the widest variety of pages in your Framy App.

## FramyApp

Framy App is the only _required_ annotation. The best place to use it is the main widget of your app. It points the place in the project where the Framy App's main file should be generated.

[main.dart](_snippets/annotations/framy_app_demo.dart.md ':include')

## FramyTheme

> FramyTheme points out the ThemeData used in the Flutter application.

#### Using with ThemeData method or field

Since Framy uses the same widgets you do, it should use the same Theme as well. Use `FramyTheme` annotations to specify the Theme you are using. Based on that, Framy will generate your typography and color palette as well as it will use that theme for any other widget in the catalog.

[main.dart](_snippets/annotations/framy_theme_demo.dart.md ':include')

!> Method annotated with FramyTheme must be public (available to use from outside the file)!

#### Using with custom theme class

Alternatively, you can use FramyTheme annotation with your own Theme class. If you have any colors (methods, fields, getters) defined in a class annotated with `FramyTheme` they will also be used in your color palette.

[theme.dart](_snippets/annotations/framy_theme_custom_demo.dart.md ':include')

!> There can be only one ThemeData accessor annotated in a project

## FramyWidget

> Annotate your Widget classes to include them in the gallery.

Framy will generate a dependencies panel which will allow the user to pass any parameters that are defined in the Widget's constructor.

[counter_title.dart](_snippets/annotations/framy_widget.dart.md ':include')

## FramyModel

> Annotate your model classes to pass more complex parameters to your widgets

FramyWidget's constructor dependencies support by default only primitive types. In many cases you will pass a custom object instead of String or int. If you want to add an option to change custom dependencies, use FramyModel annotation with your model class.

[user.dart](_snippets/annotations/framy_model.dart.md ':include')

You can annotate enums the same way:

[gender.dart](_snippets/annotations/framy_model_enum.dart.md ':include')

!> If your class uses other custom classes (e.g. Address in User), the subclasses have to be annotated with @framyModel as well

## FramyPreset

> Define dependency presets to speed up testing parameters to your widgets

In cases when your models have a lot of dependencies and it would be a big hustle to click them all through, you can define a preset object models which will be accessible in dependencies panel.

[user.framy.dart](_snippets/annotations/framy_preset.dart.md ':include')

Since presets will be part of your normal source code, we recommend having them in a separate file, e.g. for User presets file `user.framy.dart` would do. :)

## FramyUseProvider

> If your widget dependency is passed by Provider and not constructor, just use @FramyUseProvider annotation

FramyUserProvider with FramyWidget will cause the generated app to pass a dependency using wrapped Provider around your widget. 

[user.framy.dart](_snippets/annotations/framy_use_provider.dart.md ':include')

See [Use Framy with Provider](https://framy.dev/#/tutorialprovider) for more.

## FramyRegisterRiverpod

> Annotate your Riverpod's Provider objects to let know Framy about them! 

```dart
@FramyRegisterRiverpod() //<--- Add this to register Riverpod's Provider
final weightEntries = Provider((ref) => [ 
      WeightEntry(DateTime(2020, 07, 01), 79, ''),
      WeightEntry(DateTime(2020, 07, 02), 78.6, ''),
    ]);
```

See [Use Framy with Riverpod](https://framy.dev/#/tutorialriverpod) for more.

## FramyUseRiverpod

> Annotate your widgets that are dependent on Riverpod's providers to customize them in FramyApp! 

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

See [Use Framy with Riverpod](https://framy.dev/#/tutorialriverpod) for more.
