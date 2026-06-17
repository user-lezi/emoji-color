# Emoji Color Dataset

This repository includes two files with emoji color data:

- `emojis.json` — a JSON array of emoji entries
- `emojis.csv` — a CSV table with the same data

## File formats

`emojis.json` contains objects like:

```json
[
  { "emoji": "🥑", "unicode": 129361, "color": [118, 179, 67, "#76b343"] },
  { "emoji": "🔴", "unicode": 128308, "color": [190, 25, 49, "#be1931"] }
]
```

Each object has:

- `emoji`: the emoji character
- `unicode`: the emoji code point
- `color`: `[r, g, b, hex]`

`emojis.csv` contains the same data as a table:

```csv
emoji,unicode,r,g,b,hex_color
"🥑",129361,118,179,67,"#76b343"
"🔴",128308,190,25,49,"#be1931"
```

## Use cases

- `emojis.json` is good for JavaScript or web projects.
- `emojis.csv` is good for Python, data analysis, or spreadsheets.

## Example

JavaScript:

```js
import emojiData from "./emojis.json";
const item = emojiData.find((entry) => entry.emoji === "🥑");
console.log(item);
```

Python:

```py
import pandas as pd

df = pd.read_csv('emojis.csv')
print(df.head())
```

## Notes

The colors were extracted by drawing each emoji on a canvas and averaging the visible pixels.
