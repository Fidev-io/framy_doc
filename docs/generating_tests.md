# Generating tests of your Widgets

> Framy can also generate golden tests for you! From now you are safe against any UI regressions!

If you are not familiar with Golden Tests, check out quick [introduction article](https://medium.com/flutter-community/flutter-golden-tests-compare-widgets-with-snapshots-27f83f266cea) by [Katarina Sheremet](https://twitter.com/kate_sheremet). 

The idea is to have automated tests which check against any UI regressions in your app so that you are safe from any unwanted changes in your app.

## Add @FramyGoldenTests annotation
First, you need to add `@FramyGodlenTests` annotation to any element in the `test` folder.  

I find creating new file named `golden_test.dart` with main function the best approach:
```dart
import 'package:framy_annotation/framy_annotation.dart';
import 'golden_test.test.framy.dart' as golden_tests;

@FramyGoldenTests()
void main() => golden_tests.main();
```

> A cool trick is to run generated tests from annotated main function.

## Run builder

Run your typical build with `flutter pub run build_runner build` or `flutter pub run build_runner watch`.

## Run your tests for the first time

Since we don't have any screenshots to compare to yet, we have to generate our points of references. To do that, just run `flutter test --update-goldens`.

After that, you should have a `test/goldens` directory with generated screenshots for all your annotated widgets!

![image](https://user-images.githubusercontent.com/16286046/89912262-a54bd380-dbf2-11ea-853a-31147a42b1ef.png)

## Be safe from UI regressions!

From now on, whenever you run `flutter test`, all your FramyWidgets will be checked if any regressions have occurred!

### More on golden tests:

* [Flutter: Golden tests — compare Widgets with Snapshots](https://medium.com/flutter-community/flutter-golden-tests-compare-widgets-with-snapshots-27f83f266cea)
* [How to run Flutter Golden (Snapshot) tests with Codemagic CI/CD](https://blog.codemagic.io/flutter-golden-tests-with-codemagic-cicd/)
* [How to run Flutter Golden (Snapshot) tests with Codemagic CI/CD. Part 2](https://blog.codemagic.io/flutter-golden-tests-with-codemagic-cicd-part-two/)
