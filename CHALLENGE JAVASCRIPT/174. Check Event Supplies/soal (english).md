# 🎯 Check Event Supplies

## Challenge Overview

**Difficulty:** `Easy`

---

## 📋 Problem Description

Write a function `checkSupplies` that takes `list1`, `list2` and `item` and returns a boolean indicating if the item is found in the combined lists.

The function combines two supply arrays for your outdoor event and checks if a specific item exists in the merged list.

---

## 🔧 Function Signature

```javascript
function checkSupplies(list1, list2, item)
```

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `list1` | `array` | First list of event supplies |
| `list2` | `array` | Second list of event supplies |
| `item` | `string` | Item name to search for |

---

## 📤 Returns

**Type:** `Boolean`

**Description:** Indicates if the item is found in the combined supply lists.

**Format:** `true` or `false`

---

## 💡 Example Usage

```javascript
// Example 1
const supplies1 = ['tent', 'sleeping bag', 'flashlight'];
const supplies2 = ['cooler', 'grill', 'chairs'];
checkSupplies(supplies1, supplies2, 'flashlight');
// Expected output: true

// Example 2
checkSupplies(supplies1, supplies2, 'umbrella');
// Expected output: false
```

---

## ✅ Requirements

- Combine both supply lists
- Search for the specified item in the merged list
- Return `true` if item exists, `false` otherwise

---

## 🎓 Skills Practiced

- Array manipulation
- Array merging/concatenation
- Search operations
- Boolean logic

---

> **Note:** This is an easy-level challenge designed to practice basic array operations and search functionality.
