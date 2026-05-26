# Country Code Dataset

Open-source country dataset containing:

- Country Name
- ISO Country Code
- Dial Code
- Local SVG Flag
- Remote SVG Flag URL
- Currency Information

This dataset is designed for:

- Flutter
- Android
- React Native
- iOS
- Web
- Backend Applications

---

# Features

- JSON based dataset
- Local SVG flag support
- Remote CDN flag support
- Cross-platform friendly
- Lightweight structure
- Easy integration
- Public open-source usage

---

# Folder Structure

```txt
country-code-dataset/
│
├── data/
│   ├── countries.json
│   └── flags/
│
├── examples/
│   ├── flutter.md
│   ├── android.md
│   ├── react-native.md
│   ├── ios.md
│   └── web.md
│
├── README.md
└── LICENSE
```

---

# JSON Structure

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

---

# Platform Integration Guides

- [Flutter Guide](./examples/flutter.md)
- [Android Guide](./examples/android.md)
- [React Native Guide](./examples/react-native.md)
- [iOS Guide](./examples/ios.md)
- [Web Guide](./examples/web.md)

---

# Use Cases

This dataset can be used for:

- Country picker
- Phone number input
- Authentication flow
- Currency selection
- Address forms
- Region selection
- FinTech applications
- Travel applications

---

# Contributions

Contributions are welcome.

Feel free to create pull requests for:

- Missing countries
- Incorrect dial codes
- Missing flags
- Currency corrections
- Dataset improvements

---

# License

Distributed under the MIT License.
See `LICENSE` for more information.
