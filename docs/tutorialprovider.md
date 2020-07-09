# Using Provider

> Often in your apps you pass dependencies by `Provider` instead of constructor. In such cases, Framy has you covered!

### Widget using Provider

Let's say you have a Widget which uses a User from Provider given up in the widget tree:
```dart
@framyWidget
class ProfilePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Consumer<User>( //<-- we need it!
      builder: (context, user, child) {
        return Column(
          children: [
            UserDataCard(user: user),
            UserEmailsView(user: user),
            WeightUnitDisplay(),
          ],
        );
      },
    );
  }
}
```
This means that the there needs to be a Provider above that widget which will give access to that User. Without that, the app will crash.

### FramyUseProvider annotation
To handle such case, you can add `FranyUseProvider` annotation to your widget specifying the type of object you want to provide. In our case, it will be a User.

```dart
@FramyUseProvider(User) //<-- Add this
@framyWidget
class ProfilePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Consumer<User>( //<-- Now we have it in Framy!
      builder: (context, user, child) {
        ...
      },
    );
  }
}
```

!> Don't forget to annotate your class with FramyModel annotation!
```dart
@framyModel
class User {
  final String firstName;
  final String lastName;
  final int age;

  User(this.firstName, this.lastName, this.age);
}
```

### Now it works!
Adding `FramyUseProvider` to your widget causes framy to wrap it with `Provider.value` and adds the given value to the dependency panel so you can work with it as it was passed by a constructor.
