# Flutter Integration Guide

This guide explains how to use the Country Code Dataset in Flutter applications.

---

# Step 1 — Download Dataset

Download:

- countries.json
- flags folder (optional)

from this repository.

---

# Step 2 — Add Assets

Create:

```txt
assets/data/
```

Place:

```txt
countries.json
```

inside it.

If using local SVG flags:

```txt
assets/data/flags/
```

Copy SVG files into flags folder.

---

# Step 3 — Update pubspec.yaml

```yaml
flutter:
  assets:
    - assets/data/
```

---

# Step 4 — Install Dependencies

If using SVG flags:

```yaml
dependencies:
  flutter_svg: ^2.0.10+1
```

Run:

```bash
flutter pub get
```

---

# Step 5 — Load JSON

```dart
import 'dart:convert';
import 'package:flutter/services.dart';

Future<List<dynamic>> loadCountries() async {
  final jsonString = await rootBundle.loadString(
    'assets/data/countries.json',
  );

  return jsonDecode(jsonString);
}
```

---

# Step 6 — Display Countries

```dart
FutureBuilder(
  future: loadCountries(),
  builder: (context, snapshot) {
    if (!snapshot.hasData) {
      return const CircularProgressIndicator();
    }

    final countries = snapshot.data as List;

    return ListView.builder(
      itemCount: countries.length,
      itemBuilder: (context, index) {
        final country = countries[index];

        return ListTile(
          leading: Image.network(
            country['flags']['remote'],
            width: 32,
          ),
          title: Text(country['name']),
          subtitle: Text(country['dial_code']),
        );
      },
    );
  },
)
```

---

# Example JSON Structure

```json
{
  "name": "India",
  "code": "IN",
  "dial_code": "+91",
  "flags": {
    "local": "flags/in.svg",
    "remote": "https://flagcdn.com/in.svg"
  }
}
```
