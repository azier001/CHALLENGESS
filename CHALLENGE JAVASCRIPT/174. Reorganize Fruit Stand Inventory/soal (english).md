# 🍎 Reorganize Fruit Stand Inventory

## 📋 Challenge Overview

**Difficulty:** `Easy`

---

## 🎯 Problem Statement

Write a function `reorganizeInventory` that takes an inventory array and returns a 2D array with rows reversed.

You're helping reorganize the fruit stand display by **flipping the inventory from bottom shelf to top shelf order**.

---

## 📥 Parameters

### `inventory` *(array)*
- A **2D array** where each row contains:
  - `[fruit name, quantity]`
  
**Example structure:**
```javascript
[
  ["apple", 10],
  ["banana", 5],
  ["orange", 8]
]
```

---

## 📤 Returns

A **2D array** with rows in reverse order.

**Format:** `[["fruit", quantity], ["fruit", quantity], ...]`

**Example output:**
```javascript
[
  ["orange", 8],
  ["banana", 5],
  ["apple", 10]
]
```

---

## 💡 Function Signature

```javascript
function reorganizeInventory(inventory) {
  // Your code here
}
```

---

## 🧪 Example Usage

### Input:
```javascript
const inventory = [
  ["apple", 10],
  ["banana", 5],
  ["orange", 8]
];

reorganizeInventory(inventory);
```

### Output:
```javascript
[
  ["orange", 8],
  ["banana", 5],
  ["apple", 10]
]
```

---

## 🔑 Key Points

- ✅ Reverse the **order of rows** (not individual elements)
- ✅ Maintain the structure of each row `[fruit, quantity]`
- ✅ Do not modify the original array (optional best practice)

---

## 🚀 Getting Started

Think about JavaScript array methods that can help you reverse the order of elements. Consider methods like `.reverse()` or iteration techniques!

Good luck! 🎉
