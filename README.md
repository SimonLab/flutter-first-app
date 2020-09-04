# flutter-first-app

Recap of https://flutter.dev/docs/get-started/codelab

## Flutter for web

Flutter can compile the application to run on your browser.
This feature is not yet `stable` so it is only available on the
beta channel (flutter channel for feature realeses: `stable`, `beta`, `dev`, `master`, see https://github.com/flutter/flutter/wiki/Flutter-build-release-channels ).

The three following command line enable a flutter app to run as a web app:

```sh
flutter channel beta
flutter upgrade
flutter config --enable-web
```

## Create a new Flutter project (using the CLI)

You can read the command line documetation for creating a new project with:

```sh
flutter create help
```

-- org define organisation which is also used to create identifier for java and ios bundle.
use reverse domain name, com.dwy.app

In our case we run:

```sh
flutter create --org com.dwyl --project-name flutter_first_app .
```

where `com.dwyl` is used to create a unique name for the compiled project using the [reverse domain name notation](https://en.wikipedia.org/wiki/Reverse_domain_name_notation)

The project is crated on the working folder `.`
You can already test the created project with `flutter run` command. This will launch the application on your connected device.
To run the application on an emulator, see the commands `flutter emulators`.
By default Flutter create a simple counter application:

![default_flutter_application](https://user-images.githubusercontent.com/6057298/92235925-66850280-eeac-11ea-8436-c1ce059c590e.png)

The code is contains in the `lib/main.dart` file.
Changing the file to:

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override

  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Welcome to Flutter!',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Welcome!'),
          centerTitle: true,
      ),
      body: Center(child: Text('Hello There'))
      )
    );
  }
}
```

Create a simple "Hello There" text display and an appBar (header) with the title "Welcome!".
The main function call the `runApp` function which takes the `MyApp` class.
This class creates a stateless widget and provide the `build` function.
The `build` function describe how to display the widget on the screen.

The widget used are linked in a Tree. We start with the `Scaffold` widget 
which creates an `appBar` and a `body`. The `appBar takes a title (define with the Text widget)
and the property `centerTitle`.
