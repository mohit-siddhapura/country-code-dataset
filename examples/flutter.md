# Flutter Integration Guide

This guide explains how to use the Country Code Dataset in Flutter applications.

---

# Step 1 — Download Dataset

Download:

- countries.json
- flags folder

from this repository.

---

# Step 2 — Add Assets

Create folders inside your Flutter project:

```txt
assets/data/
```

Place:

```txt
countries.json
```

inside:

```txt
assets/data/
```

Place SVG flags inside:

```txt
assets/data/flags/
```

Final structure:

```txt
assets/
 └── data/
      ├── countries.json
      └── flags/
```

---

# Step 3 — Update pubspec.yaml

```yaml
flutter:
  assets:
    - assets/data/
```

---

# Step 4 — Install Dependencies

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
import 'package:flutter_svg/flutter_svg.dart';

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
          leading: SvgPicture.asset(
            'assets/data/${country['flags']['local']}',
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
  "name": "Anguilla",
  "code": "AI",
  "dial_code": "+1264",
  "flags": {
    "local": "flags/ai.svg",
    "remote": "https://flagcdn.com/ai.svg"
  },
  "currency_details": {
    "name": "Eastern Caribbean dollar",
    "code": "XCD",
    "symbol": "$"
  }
}
```
