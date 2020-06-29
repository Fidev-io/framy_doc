```dart
@FramyUseProvider(User)
@framyWidget
class ProfilePage extends StatelessWidget {

  @override
  Widget build(BuildContext context) {
    return Consumer<User>( //<-- Framy will take care of this
      builder: (context, user, child) {
        return ...;
      },
    );
  }
}
```