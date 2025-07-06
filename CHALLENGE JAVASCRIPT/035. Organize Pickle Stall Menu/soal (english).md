# 🥒 Pickle Stall Menu Organization Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Help a curious visitor organize and display pickles at a traditional Bashkir village market by creating a function that sorts pickles by price and formats them into a beautiful menu display.

---

## 🎯 Objective

Create a function named `organizePickleStall` that takes pickle names and their corresponding prices, then organizes them into a well-formatted menu sorted by price.

---

## 📝 Function Specification

### Function Name
```javascript
organizePickleStall(pickleNames, prices)
```

### Parameters

| Parameter | Type | Description | Example |
|-----------|------|-------------|---------|
| `pickleNames` | `Array<string>` | An array of pickle names | `['Cucumber', 'Tomato', 'Cabbage']` |
| `prices` | `Array<number>` | An array of corresponding prices | `[2.5, 3.0, 1.8]` |

### Return Value
- **Type:** `string`
- **Description:** A formatted menu string with header, sorted pickle items, and footer

---

## 🔧 Requirements

The function must perform the following operations:

1. **Sort pickles by price** in ascending order (lowest to highest)
2. **Maintain pairing** between pickle names and their prices during sorting
3. **Create formatted menu** with each pickle and price on a new line
4. **Add header and footer** to create a proper menu appearance

---

## 📊 Expected Behavior

### Input Example
```javascript
pickleNames = ['Cucumber', 'Tomato', 'Cabbage']
prices = [2.5, 3.0, 1.8]
```

### Expected Output Structure
```
[Header]
Cabbage - $1.8
Cucumber - $2.5
Tomato - $3.0
[Footer]
```

---

## ⚠️ Important Notes

- **Data Integrity:** Ensure pickle names and prices remain correctly paired after sorting
- **Formatting:** Create a visually appealing menu with proper structure
- **Sorting:** Always sort in ascending order (cheapest first)
- **String Output:** Return a single, well-formatted string

---

## 🏷️ Tags

`Array Manipulation` `Sorting` `String Formatting` `Data Pairing` `Market Simulation`
