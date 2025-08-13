# 🐟 Sorting Fish by Size Challenge

## 📋 Challenge Overview
**Difficulty Level:** `Easy`

Create a function that sorts fish names based on their natural size categories, from smallest to largest.

---

## 🎯 Objective
Implement a function named `sortFishBySize` that organizes an array of fish names according to their size hierarchy.

---

## 📏 Fish Size Categories

The sorting should follow this size order (ascending):

| Size Category | Fish Type | Symbol |
|---------------|-----------|---------|
| **Small** | Sardine | 🐟 |
| **Medium** | Trout | 🐠 |
| **Large** | Salmon | 🎣 |
| **Extra Large** | Tuna | 🐋 |

---

## 🔧 Function Specification

### Function Signature
```javascript
function sortFishBySize(fishList)
```

### Parameters
- **`fishList`** *(array)*: An array of strings containing fish names
  - Accepted values: `"Sardine"`, `"Trout"`, `"Salmon"`, `"Tuna"`

### Return Value
- **Returns:** A new array with fish names sorted by size (small → extra large)

---

## 📝 Example Usage

```javascript
// Input example
const fishArray = ["Tuna", "Sardine", "Salmon", "Trout"];

// Expected output
const sortedFish = sortFishBySize(fishArray);
console.log(sortedFish);
// Output: ["Sardine", "Trout", "Salmon", "Tuna"]
```

---

## ✅ Requirements Summary

- [x] Function name must be exactly `sortFishBySize`
- [x] Accept one parameter: `fishList` (array)
- [x] Sort fish by size: Sardine → Trout → Salmon → Tuna
- [x] Return the sorted array
- [x] Maintain ascending order (smallest to largest)

---

## 🎪 Challenge Tags
`#Array` `#Sorting` `#String-Manipulation` `#Easy-Level`
