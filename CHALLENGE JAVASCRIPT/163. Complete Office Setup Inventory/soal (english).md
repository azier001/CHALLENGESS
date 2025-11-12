# 📦 Complete Office Setup Inventory

## Challenge Overview

**Difficulty Level:** `Easy` 🟢

---

## 🎯 Problem Statement

You're setting up your home office workspace and need to create a complete inventory by combining your current supplies with new purchases.

Write a function that efficiently merges your existing office supplies with newly purchased items to maintain an organized inventory list.

---

## 📋 Function Specification

### Function Name
```javascript
combineOfficeSupplies(existingItems, newItems)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `existingItems` | `array` | Current office supplies you already have |
| `newItems` | `array` | New supplies you just purchased |

### Return Value

**Type:** `array`

**Format:** `['item1', 'item2', 'item3']`

**Description:** A combined array with existing items listed first, followed by new items.

---

## 💡 Example Usage

```javascript
// Example 1: Basic combination
const existing = ['pen', 'notebook', 'stapler'];
const newPurchases = ['printer paper', 'markers', 'sticky notes'];

combineOfficeSupplies(existing, newPurchases);
// Returns: ['pen', 'notebook', 'stapler', 'printer paper', 'markers', 'sticky notes']
```

```javascript
// Example 2: Empty existing inventory
const existing = [];
const newPurchases = ['desk lamp', 'mouse pad'];

combineOfficeSupplies(existing, newPurchases);
// Returns: ['desk lamp', 'mouse pad']
```

```javascript
// Example 3: No new purchases
const existing = ['keyboard', 'monitor'];
const newPurchases = [];

combineOfficeSupplies(existing, newPurchases);
// Returns: ['keyboard', 'monitor']
```

---

## ✅ Requirements

- ✓ Existing items must appear **first** in the combined array
- ✓ New items must appear **after** all existing items
- ✓ Maintain the original order of items within each category
- ✓ Handle empty arrays gracefully

---

## 🚀 Getting Started

Start by thinking about:
- How to merge two arrays in JavaScript
- What array methods are available for combining arrays
- How to maintain the correct order

Good luck with your office inventory system! 🎉
