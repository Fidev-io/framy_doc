# Using Built_value

> Framy provides support for models generated with Built_value package out of the box!

## Add framyModel annotation

Annotating models using Built_value works without any extra actions, just add `@framyModel` annotation to the main class
```dart
@framyModel
abstract class BuiltUser implements Built<BuiltUser, BuiltUserBuilder> {
  String get firstName;

  String get lastName;

  BuiltUser._();

  factory BuiltUser([updates(BuiltUserBuilder b)]) = _$BuiltUser;
}
```

## Use the model

Framy will let you customize the params the same way you would use a model which gets values from constructor.