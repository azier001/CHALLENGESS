# 🦄 Lily's Pony Lineup

## Challenge Level
**Easy** 🟢

---

## 📋 Overview

Create a function named `arrangePonies` that helps Lily arrange her toy ponies in a special order. Lily has a group of ponies already lined up and wants to add more ponies to the end of the line.

---

## 🎯 Objective

The function should create a new array that combines both groups of ponies, ensuring that the ponies from `poniesToAdd` appear **after** the ponies from `initialPonies` in the final arrangement.

---

## 📝 Function Signature

```javascript
function arrangePonies(initialPonies, poniesToAdd)
```

---

## 🔧 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `initialPonies` | `array` | An array of strings representing the names of the ponies already lined up |
| `poniesToAdd` | `array` | An array of strings representing the names of the ponies Lily wants to add to the line |

---

## 📤 Return Value

**Type:** `array`

An array of strings representing the final arrangement of Lily's ponies, with the ponies from `poniesToAdd` appearing after the ponies from `initialPonies`.

---

## ⚙️ Requirements

- ✅ The function should work correctly if either of the input arrays is empty
- ✅ If there are any duplicate pony names between the two arrays, the duplicates should be included in the final array
- ✅ The order must be preserved: `initialPonies` first, then `poniesToAdd`

---

## 💡 Example Usage

```javascript
// Example 1: Basic usage
const initial = ['Rainbow', 'Twilight', 'Pinkie'];
const toAdd = ['Fluttershy', 'Rarity'];
arrangePonies(initial, toAdd);
// Expected output: ['Rainbow', 'Twilight', 'Pinkie', 'Fluttershy', 'Rarity']

// Example 2: With duplicates
const initial = ['Rainbow', 'Twilight'];
const toAdd = ['Rainbow', 'Applejack'];
arrangePonies(initial, toAdd);
// Expected output: ['Rainbow', 'Twilight', 'Rainbow', 'Applejack']

// Example 3: Empty arrays
arrangePonies([], ['Fluttershy']);
// Expected output: ['Fluttershy']

arrangePonies(['Rainbow'], []);
// Expected output: ['Rainbow']
```

---

## 🎨 Tips

- Consider using array methods for combining arrays
- Remember to handle edge cases with empty arrays
- Duplicates are allowed and should be preserved

---

**Happy Coding!** 🚀
