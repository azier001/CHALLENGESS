# 🎨 Whimsical Tassel Base Converter

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function that converts decimal numbers to different bases based on magical tassel colors! Each tassel color represents a unique number system, making this a colorful journey through different base conversions.

---

## 🎯 Function Specification

### Function Name
```javascript
tasselBaseConverter(tasselColor, number)
```

### 🌈 Tassel Color Mapping

The tassel color determines the target base for conversion:

| Tassel Color | Base System | Base Number |
|--------------|-------------|-------------|
| 🔴 **red**   | Binary      | Base 2      |
| 🔵 **blue**  | Hexadecimal | Base 16     |
| 🟢 **green** | Octal       | Base 8      |

---

## 📝 Parameters

### `tasselColor` (string)
- **Description:** The color of the tassel that determines the target base
- **Valid Values:** 
  - `"red"` - for binary conversion
  - `"blue"` - for hexadecimal conversion  
  - `"green"` - for octal conversion
- **Type:** String

### `number` (string)
- **Description:** The decimal number to be converted
- **Range:** 0 to 10,000 (inclusive)
- **Type:** String
- **Format:** Decimal representation

---

## 📤 Return Value

- **Type:** String
- **Description:** The converted number in the base corresponding to the `tasselColor`
- **Format:** String representation of the number in the target base

---

## 💡 Examples

```javascript
// Binary conversion (red tassel)
tasselBaseConverter("red", "10")    // Returns: "1010"
tasselBaseConverter("red", "255")   // Returns: "11111111"

// Hexadecimal conversion (blue tassel)
tasselBaseConverter("blue", "255")  // Returns: "ff"
tasselBaseConverter("blue", "4096") // Returns: "1000"

// Octal conversion (green tassel)
tasselBaseConverter("green", "64")  // Returns: "100"
tasselBaseConverter("green", "512") // Returns: "1000"
```

---

## ✨ Key Features

- 🎨 **Color-coded base selection** - Intuitive mapping of colors to number systems
- 🔢 **Multiple base support** - Binary, Octal, and Hexadecimal conversions
- 📊 **Wide range support** - Handles numbers from 0 to 10,000
- 🎯 **Simple interface** - Easy-to-use function with clear parameters

---

## 🚀 Getting Started

1. Implement the `tasselBaseConverter` function
2. Handle the three tassel colors: red, blue, and green
3. Convert the decimal input to the appropriate base
4. Return the result as a string
5. Test with various input combinations!

> **Note:** This challenge focuses on understanding different number base systems while adding a whimsical twist with colorful tassels! 🎭
