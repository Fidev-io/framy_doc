# Getting started

## Packages

In order to use Framy, you will need two following packages:

* [framy_annotation](https://pub.dev/packages/framy_annotation) - A package containing annotation classes.
* [framy_generator](https://pub.dev/packages/framy_generator) - A powerful code generator which creates whole application based on the annotations used.

| Package                                                                            | Pub                                                                                                    |
| ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| [framy_annotation](https://pub.dev/packages/framy_annotation) | [![pub package](https://img.shields.io/pub/v/framy_annotation.svg)](https://pub.dev/packages/framy_annotation) |
| [framy_generator](https://pub.dev/packages/framy_generator)   | [![pub package](https://img.shields.io/pub/v/framy_generator.svg)](https://pub.dev/packages/framy_generator) |

## Installation

### Get packages

To use Framy, you will need your typical build_runner/code-generator setup.  
First, install `build_runner` and Framy by adding them to your `pubspec.yaml` file:  

[pubspec.yaml](_snippets/gettingstarted/framy_pubspec.yaml.md ':include')


### Add the @FramyApp annotation
`@FramyApp` annotation is coming from `framy_annotations` package. It's only purpose is to specify where the Framy app should be generated. Without this, the generator will not work. There should be only one `@FramyApp` annotation for the project.

[main.dart](_snippets/gettingstarted/annotation_framy_app_demo.dart.md ':include')


### Run the generator
You can either run
`flutter pub run build_runner build` to generate the app from the current code or `flutter pub run build_runner watch` to keep listening to changes in the source code and update the Framy app accordingly.

### Run the generated app
Generator creates a new main file. Run `flutter run lib/main.app.framy.dart` to use Framy!

![ezgif com-video-to-gif (16)](https://user-images.githubusercontent.com/16286046/86018379-8d930400-ba25-11ea-9a85-a585c3b2b84f.gif)
