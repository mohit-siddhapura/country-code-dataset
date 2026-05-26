# Web Integration Guide

This guide explains how to use the Country Code Dataset in web applications.

---

# Step 1 — Download Dataset

Download:

- countries.json
- flags folder

from this repository.

---

# Step 2 — Add Assets

Place:

```txt
countries.json
```

inside your public folder.

Place SVG flags inside:

```txt
public/flags/
```

---

# Step 3 — Fetch JSON

```javascript
async function loadCountries() {
  const response = await fetch('/countries.json');

  return response.json();
}
```

---

# Step 4 — Render Countries

```javascript
const countries = await loadCountries();

countries.forEach((country) => {
  const item = document.createElement('div');

  item.innerHTML = `
    <img src="${country.flags.remote}" width="32" />
    <span>${country.name}</span>
    <span>${country.dial_code}</span>
    <span>${country.currency_details.code}</span>
  `;

  document.body.appendChild(item);
});
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
