# React Native Integration Guide

This guide explains how to use the Country Code Dataset in React Native applications.

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
assets/data/
```

Place:

```txt
countries.json
```

inside it.

Place SVG flags inside:

```txt
assets/data/flags/
```

---

# Step 3 — Import JSON

```javascript
import countries from './assets/data/countries.json';
```

---

# Step 4 — Render Countries

```javascript
<FlatList
  data={countries}
  keyExtractor={(item) => item.code}
  renderItem={({ item }) => (
    <View>
      <Image
        source={{ uri: item.flags.remote }}
        style={{ width: 32, height: 24 }}
      />

      <Text>{item.name}</Text>

      <Text>{item.dial_code}</Text>

      <Text>{item.currency_details.code}</Text>
    </View>
  )}
/>
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
