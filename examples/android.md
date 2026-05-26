# Android Integration Guide

This guide explains how to use the Country Code Dataset in Android applications.

---

# Step 1 — Download Dataset

Download:

- countries.json
- flags folder

from this repository.

---

# Step 2 — Add Assets

Create:

```txt
app/src/main/assets/
```

Place:

```txt
countries.json
```

inside assets folder.

Create:

```txt
app/src/main/assets/flags/
```

Place SVG flags inside it.

Final structure:

```txt
app/
 └── src/
      └── main/
           └── assets/
                ├── countries.json
                └── flags/
```

---

# Step 3 — Add Dependencies

## Gson

```gradle
implementation 'com.google.code.gson:gson:2.10.1'
```

## Coil

```gradle
implementation("io.coil-kt:coil-compose:2.6.0")
```

---

# Step 4 — Read JSON

```kotlin
val json = context.assets
    .open("countries.json")
    .bufferedReader()
    .use { it.readText() }
```

---

# Step 5 — Create Models

```kotlin
data class Country(
    val name: String,
    val code: String,
    val dial_code: String,
    val flags: Flags,
    val currency_details: CurrencyDetails
)

data class Flags(
    val local: String,
    val remote: String
)

data class CurrencyDetails(
    val name: String,
    val code: String,
    val symbol: String
)
```

---

# Step 6 — Parse JSON

```kotlin
val type = object : TypeToken<List<Country>>() {}.type

val countries: List<Country> =
    Gson().fromJson(json, type)
```

---

# Step 7 — Display Flag

```kotlin
AsyncImage(
    model = country.flags.remote,
    contentDescription = null
)
```
