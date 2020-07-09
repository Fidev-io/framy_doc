# Framy

[![Example apps](https://img.shields.io/badge/Github%20Pages-Example%20Apps-brightgreen)](https://fidev-io.github.io/framy/)
[![Acceptance tests](https://github.com/Fidev-io/framy/workflows/Acceptance%20tests/badge.svg?event=push)](https://github.com/Fidev-io/framy/actions?query=workflow%3A%22Acceptance+tests%22)
[![Unit tests](https://github.com/Fidev-io/framy/workflows/Unit%20tests/badge.svg?event=push)](https://github.com/Fidev-io/framy/actions?query=workflow%3A%22Unit+tests%22)
[<img src="https://img.shields.io/badge/slack-FramyChat-yellow.svg?logo=slack">](https://join.slack.com/t/framy/shared_invite/zt-ffqv9tgl-kpn8cLNnPtPTeEK_Pa5ckA)
[![License: AGPL v3](https://img.shields.io/badge/License-AGPL%20v3-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)  

A convenient code generator for app styleguide, gallery, wireframes and/or storyboard.

👉 [Official documentation](https://framy.dev) 👈  


## Packages

In order to use Framy, you will need two following packages:

* [framy_annotation](https://pub.dev/packages/framy_annotation) - A package containing annotation classes.
* [framy_generator](https://pub.dev/packages/framy_generator) - A powerful code generator which creates whole application based on the annotations used.

| Package                                                                            | Pub                                                                                                    |
| ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| [framy_annotation](https://pub.dev/packages/framy_annotation) | [![pub package](https://img.shields.io/pub/v/framy_annotation.svg)](https://pub.dev/packages/framy_annotation) |
| [framy_generator](https://pub.dev/packages/framy_generator)   | [![pub package](https://img.shields.io/pub/v/framy_generator.svg)](https://pub.dev/packages/framy_generator) |

## Examples
* [Counter app](framy.dev/#/counter)
* [WeightTracker](framy.dev/#/weighttracker)

![ezgif com-video-to-gif (16)](https://user-images.githubusercontent.com/16286046/86018379-8d930400-ba25-11ea-9a85-a585c3b2b84f.gif)

## Idea

The idea behind Framy is to allow developers, designers, testers, managers and clients to easily access the components used in the Flutter app.

Framy is annotation-driven tool based on which you can generate: 
* a style guide describing the theme of your app
* a component gallery showing the widgets you have written in out-of-context way
* a playground for testing widgets with a variety of dependencies
* and much more coming soon...


### What makes Framy special?
* Fully responsive
  * The generated application is mobile, tablet, desktop and web friendly. Framy generates a separate main file with a separate MaterialApp but it does use the same widgets you are using in your own Flutter app.
* Standalone
  * You can easily host generated app the way you prefer or just run it locally. (Automated hosting of Framy App is planned as well 😉)
* Non-invasive
  * Framy doesn't require using any special widgets to be working. There is no `Framy` widget to wrap your app in so it doesn't affect your actual product. Only annotations.


## Installation

### Get packages

To use Framy, you will need your typical build_runner/code-generator setup.  
First, install `build_runner` and Framy by adding them to your `pubspec.yaml` file:  

```yaml
dependencies:
  framy_annotation:

dev_dependencies:
  build_runner:
  framy_generator:
```

### Add the @FramyApp annotation
`@FramyApp` annotation is coming from `framy_annotations` package. It's only purpose is to specify where the Framy app should be generated. Without this, the generator will not work. There should be only one `@FramyApp` annotation for the project.

```dart
@FramyApp() //<--- Add this annotation
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(...);
  }
}
```

### Run the generator
You can either run
`flutter pub run build_runner build` to generate the app from the current code or `flutter pub run build_runner watch` to keep listening to changes in the source code and update the Framy app accordingly.

### Run the generated app
Generator creates a new main file. Run `flutter run lib/main.app.framy.dart` to use Framy!


# Maintenance
Our purpose is to make this tool as comprehensive as possible. We are trying to constantly improve it, add new features, handle new cases and fix any bugs.

If there is any use-case that we do not support and you think we should, feel free to [submit an issue](https://github.com/Fidev-io/framy/issues/new) on GitHub. 🙂

