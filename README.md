# magic_button

A customizable Flutter button widget that displays an animated gradient border. The gradient rotates around the button, creating an attractive visual effect. The button also includes hover animations and supports both text and icon content.

![Magic Button](https://github.com/vhdrjb/flutter_magic_button/blob/main/images/magic_button.gif)

## Features

- Animated gradient border that rotates around the button
- Hover effects with scaling animation
- Customizable colors, border radius, and animation duration
- Support for text labels, icons, or both
- Platform-aware hover detection (mouse on desktop, long press on mobile)
- Customizable text and icon styles for both default and hover states

## Installation

Add this to your package's `pubspec.yaml` file:

```yaml
dependencies:
  magic_button: ^1.0.0
```

Then run:

```
flutter pub get
```

## Usage

### Basic Usage

```dart
import 'package:magic_button/magic_button.dart';

MagicButton(
  label: "Generate",
  icon: Icons.auto_awesome,
  onPress: () {
    print("Button pressed!");
  },
)
```

### Customization Examples

#### Custom Colors

```dart
MagicButton(
  label: "Submit",
  buttonColor: Color(0xFF1E1637),
  animatingColors: [
    Color(0xFFcc00ff),
    Color(0xFF4d00ff),
    Color(0xFF00b2ff),
  ],
  onPress: () {
    // Handle button press
  },
)
```

#### Custom Border Radius and Animation Duration

```dart
MagicButton(
  label: "Login",
  icon: Icons.login,
  borderRadius: BorderRadius.circular(12),
  animationDuration: Duration(seconds: 3),
  onPress: () {
    // Handle login
  },
)
```

#### Custom Text and Icon Styles

```dart
MagicButton(
  label: "Download",
  icon: Icons.download,
  labelStyle: TextStyle(
    color: Colors.white,
    fontSize: 16,
    fontWeight: FontWeight.bold,
  ),
  labelHoveredStyle: TextStyle(
    color: Colors.yellow,
    fontSize: 16,
    fontWeight: FontWeight.bold,
  ),
  iconColor: Colors.white,
  iconHoverColor: Colors.yellow,
  iconSize: 24,
  onPress: () {
    // Handle download
  },
)
```

## Properties

| Property | Type | Description | Default |
|----------|------|-------------|---------|
| label | String? | Text displayed on the button | null |
| labelStyle | TextStyle? | Style for the label text | White, size 18, weight 500 |
| labelHoveredStyle | TextStyle? | Style for the label text when hovered | Same as labelStyle |
| icon | IconData? | Icon displayed on the button | null |
| iconColor | Color? | Color of the icon | Colors.white |
| iconHoverColor | Color? | Color of the icon when hovered | Colors.amber |
| iconSize | double? | Size of the icon | 20 |
| animationDuration | Duration | Duration of one complete gradient rotation | 2 seconds |
| borderRadius | BorderRadius? | Border radius of the button | null |
| buttonColor | Color? | Background color of the button | Color(0xE61E1637) |
| animatingColors | List<Color>? | Colors used in the gradient animation | [Purple, Blue, Light Blue] |
| padding | double? | Padding between border and button content | 4 |
| onPress | VoidCallback? | Function called when the button is pressed | null |

## Example App

```dart
import 'package:flutter/material.dart';
import 'package:magic_button/magic_button.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Magic Button Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        brightness: Brightness.dark,
      ),
      home: Scaffold(
        backgroundColor: Colors.black,
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              MagicButton(
                label: "Generate",
                icon: Icons.auto_awesome,
                onPress: () {
                  print("Generate button pressed!");
                },
              ),
              SizedBox(height: 20),
              MagicButton(
                label: "Download",
                icon: Icons.download,
                borderRadius: BorderRadius.circular(8),
                buttonColor: Color(0xFF2D1D4E),
                animatingColors: [
                  Color(0xFF00FFFF),
                  Color(0xFF00BFFF),
                  Color(0xFF1E90FF),
                ],
                onPress: () {
                  print("Download button pressed!");
                },
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```

## Platform Support

- ✅ Android
- ✅ iOS
- ✅ Web
- ✅ Windows
- ✅ macOS
- ✅ Linux

## Additional Notes

- The hover effect automatically uses `MouseRegion` on desktop platforms and fallbacks to `GestureDetector` with long press on mobile platforms.
- For the best visual effect, use the button against a dark background.
- The gradient border automatically adapts to the button's size.

## License

```
MIT License

Copyright (c) 2025 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
