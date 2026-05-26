# iOS Integration Guide

This guide explains how to use the Country Code Dataset in iOS applications.

---

# Step 1 — Download Dataset

Download:

- countries.json
- flags folder

from this repository.

---

# Step 2 — Add Assets To Xcode

Drag:

```txt
countries.json
```

and:

```txt
flags/
```

into your Xcode project.

Enable:
- Copy items if needed

---

# Step 3 — Create Models

```swift
struct Country: Codable {
    let name: String
    let code: String
    let dial_code: String
    let flags: Flags
    let currency_details: CurrencyDetails
}

struct Flags: Codable {
    let local: String
    let remote: String
}

struct CurrencyDetails: Codable {
    let name: String
    let code: String
    let symbol: String
}
```

---

# Step 4 — Read JSON

```swift
guard let url = Bundle.main.url(
    forResource: "countries",
    withExtension: "json"
) else {
    return
}

let data = try Data(contentsOf: url)

let countries = try JSONDecoder()
    .decode([Country].self, from: data)
```
