# 🌷 Ellen's Tulip Color Finder

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Ellen is tending to her colorful tulip garden on a sunny spring afternoon. She wants to identify the color of a specific tulip in her garden. Your task is to create a function that will help Ellen find the color of the tulip at a given position.

---

## 🎯 Objective

Create a function named `findTulipColor` that receives two parameters and helps Ellen identify tulip colors in her garden.

### Function Signature
```javascript
function findTulipColor(garden, position)
```

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `garden` | `Array<string>` | An array of strings representing the colors of tulips in Ellen's garden |
| `position` | `number` | An integer representing the position of the tulip Ellen wants to check (**1-based index**) |

---

## 📤 Return Value

The function returns a **string** with one of the following outcomes:

### ✅ Valid Position
- Returns the **color** of the tulip at the specified position

### ❌ Invalid Position Cases
- **Position < 1:** `"Oh no! That's not a valid tulip position, Ellen!"`
- **Position > garden length:** `"Oops! Your garden isn't that big, Ellen!"`

---

## 📏 Validation Rules

> ⚠️ **Important:** The position uses **1-based indexing** (first tulip is at position 1, not 0)

1. **Position too low** (`position < 1`)
   - Return: `"Oh no! That's not a valid tulip position, Ellen!"`

2. **Position too high** (`position > garden.length`)
   - Return: `"Oops! Your garden isn't that big, Ellen!"`

3. **Valid position** (`1 ≤ position ≤ garden.length`)
   - Return: The tulip color at that position

---

## 💡 Example Usage

```javascript
// Example garden
const garden = ["red", "yellow", "pink", "purple", "white"];

// Test cases
findTulipColor(garden, 1);    // Returns: "red"
findTulipColor(garden, 3);    // Returns: "pink"
findTulipColor(garden, 0);    // Returns: "Oh no! That's not a valid tulip position, Ellen!"
findTulipColor(garden, 6);    // Returns: "Oops! Your garden isn't that big, Ellen!"
```

---

## 🧠 Key Points to Remember

- 🔢 **1-based indexing:** Position 1 corresponds to `garden[0]`
- 🌷 **Garden array:** Contains tulip colors as strings
- ✅ **Validation first:** Always check position validity before accessing the array
- 📝 **Exact messages:** Use the specified error messages exactly as written

---

## 🎨 Visual Representation

```
Ellen's Garden (1-based indexing):
Position:  1      2        3       4         5
Garden:  ["red", "yellow", "pink", "purple", "white"]
Index:     0      1        2       3         4
```

*Happy coding! Help Ellen find her beautiful tulips! 🌷*
