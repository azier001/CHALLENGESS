# 🧭 Reverse Explorer's Path and Inventory

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function that helps an explorer retrace their steps and safely return to their starting point. This challenge combines string manipulation and array operations to simulate a real-world navigation scenario.

---

## 🎯 Objective

Implement a function named `reverseExplorerPath` that processes an explorer's journey data and provides the reverse path home along with a reorganized inventory.

### 📥 Function Signature

```javascript
function reverseExplorerPath(path, inventory)
```

---

## 🔧 Parameters

### `path` (string)
- **Description:** A sequence of directional commands
- **Format:** Single characters representing cardinal directions
  - `'N'` → North ⬆️
  - `'S'` → South ⬇️  
  - `'E'` → East ➡️
  - `'W'` → West ⬅️
- **Constraints:** 
  - Length: 1 to 10 characters
  - Only contains valid direction letters

### `inventory` (array of strings)
- **Description:** Collection of items gathered during exploration
- **Format:** Array of item names
- **Constraints:**
  - Size: 0 to 5 elements
  - Each item: up to 10 lowercase letters
  - Example: `["compass", "map", "torch"]`

---

## 📤 Return Value

The function returns an **array** with exactly **two elements**:

```javascript
[reversedPath, reversedInventory]
```

1. **`reversedPath`** (string): Original path reversed character by character
2. **`reversedInventory`** (array): Original inventory with items in reverse order

---

## 💡 Example Usage

```javascript
// Example 1: Basic exploration
const path1 = "NEW";
const inventory1 = ["rope", "food", "water"];
const result1 = reverseExplorerPath(path1, inventory1);
// Returns: ["WEN", ["water", "food", "rope"]]

// Example 2: Empty inventory
const path2 = "NSEW";
const inventory2 = [];
const result2 = reverseExplorerPath(path2, inventory2);
// Returns: ["WESN", []]

// Example 3: Single direction
const path3 = "N";
const inventory3 = ["key"];
const result3 = reverseExplorerPath(path3, inventory3);
// Returns: ["N", ["key"]]
```

---

## 🧠 Algorithm Hints

### For Path Reversal:
- Use string methods like `split()`, `reverse()`, and `join()`
- Or iterate through the string backwards

### For Inventory Reversal:
- Use the array `reverse()` method
- Or create a new array by iterating backwards

### Implementation Approach:
```javascript
function reverseExplorerPath(path, inventory) {
    // Step 1: Reverse the path string
    // Step 2: Reverse the inventory array
    // Step 3: Return both results as an array
}
```

---

## ✅ Success Criteria

- [x] Function correctly reverses the path string
- [x] Function correctly reverses the inventory array  
- [x] Returns results in the specified format `[string, array]`
- [x] Handles edge cases (empty inventory, single character path)
- [x] Respects all parameter constraints

---

## 🔍 Edge Cases to Consider

- **Empty inventory:** `inventory = []`
- **Single direction:** `path = "N"`
- **Maximum path length:** `path = "NEWSNEWSNE"` (10 chars)
- **Maximum inventory:** 5 items with 10 characters each

---

*Happy coding, explorer! 🗺️✨*
