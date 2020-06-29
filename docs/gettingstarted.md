# Getting started


## Packages

In order to use framy, you will need two following packages:

* [framy_annotation](https://github.com/Fidev-io/framy/tree/master/framy_annotation) - A package containing annotation classes.
* [framy_generator](https://github.com/Fidev-io/framy/tree/master/framy_generator) - A powerful code generator which creates whole application based on the annotations used.

## Installation

### Get packages

To use Framy, you will need your typical build_runner/code-generator setup.  
First, install `build_runner` and Framy by adding them to your `pubspec.yaml` file:  

[pubspec.yaml](_snippets/getting_started/framy_pubspec.yaml.md ':include')


### Add the @FramyApp annotation
`@FramyApp` annotation is coming from `framy_annotations` package. It's only purpose is to specify where the Framy app should be generated. Without this, the generator will not work. There should be only one `@FramyApp` annotation for the project.

[main.dart](_snippets/annotation_framy_app_demo.dart.md ':include')


### Run the generator
You can either run
`flutter pub run build_runner build` to generate the app from the current code or `flutter pub run build_runner watch` to keep listening to changes in the source code and update the Framy app accordingly.
