# 🧳 Airport Packing Dilemma

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

You are a traveler at an airport check-in counter, trying to fit your belongings into your carry-on bag. Your mission is to create a smart packing assistant that determines whether all your items can fit based on your bag's capacity.

---

## 🎯 Objective

Create a function named `canFitInBag` that intelligently compares the number of items against the bag's size-based capacity and returns whether everything fits.

---

## 📝 Function Specifications

### Function Name
```javascript
canFitInBag(items, bagSize)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `items` | `Array<string>` | An array of strings representing the items you want to pack |
| `bagSize` | `string` | The size of your bag: `"small"`, `"medium"`, or `"large"` |

### Return Value
- **Type:** `boolean`
- **Returns:** 
  - `true` if all items can fit in the bag
  - `false` if items exceed the bag's capacity

---

## 📏 Bag Capacity Rules

The bag capacity varies based on size:

| 🎒 Bag Size | 📦 Maximum Items | Icon |
|-------------|------------------|------|
| **Small** | 3 items | 🎒 |
| **Medium** | 5 items | 🧳 |
| **Large** | 7 items | 🛄 |

---

## 🔧 Implementation Requirements

### Key Points to Remember:
- ✅ Use **string comparison** for bag size validation
- ✅ Use **array length** to count the number of items
- ✅ Compare item count against size-specific capacity limits
- ✅ Return boolean result based on comparison

### Logic Flow:
1. Determine bag capacity based on `bagSize` parameter
2. Count the number of items in the `items` array
3. Compare item count with bag capacity
4. Return `true` if items ≤ capacity, `false` otherwise

---

## 💡 Example Usage

```javascript
// Example 1: Items fit in medium bag
const items1 = ["shirt", "pants", "shoes", "book"];
const result1 = canFitInBag(items1, "medium"); // Should return true (4 ≤ 5)

// Example 2: Too many items for small bag
const items2 = ["laptop", "charger", "headphones", "notebook", "pen"];
const result2 = canFitInBag(items2, "small"); // Should return false (5 > 3)

// Example 3: Perfect fit for large bag
const items3 = ["camera", "lens", "tripod", "batteries", "memory card", "cleaning kit", "manual"];
const result3 = canFitInBag(items3, "large"); // Should return true (7 = 7)
```

---

## 🚀 Ready to Code?

Now it's your turn to implement the `canFitInBag` function! Remember to handle all three bag sizes and ensure your logic correctly compares the item count with the appropriate capacity limit.

**Good luck, traveler!** ✈️
