# 🌦️ WMO Weather JSON

This project provides an open-source JSON dataset mapping **WMO Present weather (from manned (code 4677) and automatic (4680) stations)** to rich, user-friendly formats for UI/UX design — including **emojis**, **FontAwesome classes**, **SVG icons**, **day/night variants**, and **alt text for background images**.

## 📦 Features

- ✅ Covers WMO Present weather codes from `0` to `99`.
- 🌙🌞 Separate **day** and **night** variations for visual clarity.
- 🎨 Includes:
  - Emojis for quick display
  - Inline SVG icons for UI embedding
  - FontAwesome class names for web frameworks
- 🧩 Includes `alt` text for accessibility and screen readers.
- 💬 Casual `"comment"` and `"long"` description fields for use in apps, dashboards, or voice interfaces.
- 🌐 CDN support for both full and per-code JSON access

## 📁 File Structure

FULL

```json
"past": {...}
"present": {
  "0": {
    "day": {
      "short": "Sunny",
      "long": "No significant cloud development observed",
      "comment": "Perfect for outdoor activities!",
      "bg_image": "0_day.jpg",
      "icon": {
        "emoji": "🌞",
        "fa": "fa-solid fa-sun",
        "svg": "<svg>...</svg>",
        "alt": "Sunny - No significant cloud development observed"
      }
    },
    "night": {
      "short": "Clear",
      ...
    }
  }
}
```

SINGLE (e.g. present weather)(Contains Single Weather Code Data)

```json
"0": {
  "day": {
    "short": "Sunny",
      ...
  },
  "night": {
    "short": "Clear",
      ...
  }
}
```

## 🚀 CDN Access 
#### Fetch all data 
```js
const response = await fetch(
    "https://cdn.jsdelivr.net/gh/w3nabil/wwjson/dataset.json"
);
const codedata = await response.json();

console.log(codedata.present[0].day.short);
```
#### Fetch Single Code data (Saves time)
```js 
const code = 0; // Present Weather Code 
const response = await fetch(
    `https://cdn.jsdelivr.net/gh/w3nabil/wwjson/mono/present/${code}.json}`
);
const codedata = await response.json();

console.log(codedata.day.short);
```

## Demo 
- [UI/UX Demo](https://w3nabil.github.io/wwjson/demo/)
- [Weather WebApp with Open Meteo API](https://ip-weather.pages.dev/)
- [Visual Data Table](https://w3nabil.github.io/wwjson/demo/table/)
  
## 🛠️ Contributing
Contributions are always welcome:

1. Fork the repo

2. Add new short, long description, svgs to `dataset.json`

3. Submit a pull request

## 📚 References 
- [The Centre for Environmental Data Analysis Artefacts Service](https://artefacts.ceda.ac.uk/badc_datadocs/surface/code.html)
- [WMO CODE TABLE 4677](https://www.nodc.noaa.gov/archive/arc0021/0002199/1.1/data/0-data/HTML/WMO-CODE/WMO4677.HTM)

## 📝 LICENSE
Copyright (c) 2025 WWJson Contributors

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
