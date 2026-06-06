# Country Code Dataset

A comprehensive open-source dataset providing country metadata for modern applications.

The dataset includes:

* Country Name
* ISO 3166-1 Alpha-2 Country Code
* International Dial Code
* Local SVG Flag Asset Path
* Remote SVG Flag URL
* Currency Information

Designed for seamless integration across:

* Flutter
* Android
* React Native
* iOS
* Web
* Backend Services

---

# Overview

Country-related data is commonly required in applications such as authentication flows, onboarding forms, country pickers, phone number inputs, payment systems, fintech products, travel applications, and international e-commerce platforms.

This project provides a clean, structured, and reusable JSON dataset that can be integrated into any application with minimal effort.

The dataset supports both offline and online flag rendering through local SVG assets and remote CDN-hosted SVG URLs.

---

# Features

* Comprehensive country metadata
* ISO country code support
* International dial code support
* Currency information included
* Local SVG flag assets
* Remote SVG flag URLs
* Cross-platform compatibility
* Offline and online flag rendering support
* Lightweight JSON structure
* Easy integration
* Open-source and community-driven

---

# Project Goals

This repository aims to provide a reliable and reusable source of country metadata that developers can integrate into applications without maintaining country, dialing code, currency, and flag information manually.

The project focuses on:

* Consistent country metadata
* Easy cross-platform integration
* Offline and online flag support
* Developer-friendly documentation
* Open-source collaboration

---

# Folder Structure

```txt
country-code-dataset/
│
├── data/
│   ├── countries.json
│   └── flags/
│
├── README.md
└── LICENSE
```

---

# Dataset Structure

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

# How to Use

1. Download or clone this repository.
2. Copy or import `data/countries.json` into your application.
3. Parse the JSON file using your preferred programming language.
4. Use the country metadata to populate country pickers, phone number inputs, address forms, and currency selectors.
5. Render flags using:

   * `flags.local` for bundled SVG assets
   * `flags.remote` for CDN-hosted SVG assets
6. Bundle the `data/flags/` directory if offline flag support is required.

---

# General Integration Notes

* Compatible with any platform capable of parsing JSON.
* Local SVG assets provide offline support.
* Remote SVG URLs help reduce application bundle size.
* Country metadata can be filtered, transformed, or extended based on application requirements.
* Suitable for mobile, web, desktop, and backend systems.

---

# Use Cases

This dataset can be used for:

* Country Picker Components
* Phone Number Input Fields
* User Registration Forms
* Authentication & Onboarding Flows
* Address Management Systems
* Currency Selection
* FinTech Applications
* Banking Applications
* Travel & Tourism Platforms
* E-commerce Applications
* Localization & Internationalization Solutions

---

# Contributions

Contributions are welcome and appreciated.

You can help improve this project by:

* Adding missing countries or territories
* Correcting dial codes
* Updating currency information
* Fixing flag assets
* Improving documentation
* Enhancing dataset quality and consistency

If you find an issue or have a suggestion, please open an issue or submit a pull request.

---

# Author

Created and maintained by **Mohit Siddhapura**.

Android & Flutter Developer passionate about building scalable mobile applications, developer tools, and open-source projects.

---

# License

This project is licensed under the MIT License.

See the `LICENSE` file for full license details.
