# 📦 Moving Box Filter by Route Cities

## Challenge Level
🔶 **Medium**

---

## 🎯 Objective

Write a function `filterItemsByRoute` that filters items from moving boxes based on city names in your westward route. The function should keep only items whose names contain any city name as a substring.

---

## 📋 Function Signature

```javascript
function filterItemsByRoute(cities, boxes)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `cities` | `Array<string>` | Array of city names along your route |
| `boxes` | `Array<Array<string>>` | 2D array where each sub-array contains item names |

### Returns

- **Type**: `Array<Array<string>>`
- **Format**: `[["item1", "item2"], ["item3"], []]`
- **Description**: 2D array with the same structure as input, containing only items that contain city names as substrings

---

## 🔍 Logic Requirements

The function should follow these steps:

1. **Iterate through each box** (sub-array) in the `boxes` array
2. **Examine each item name** within the current box
3. **Check for substring match** (case-insensitive):
   - Determine if the item name contains any city name from the `cities` array
4. **Keep matching items** while maintaining the original box structure
5. **Return the filtered 2D array** with the same number of boxes as the input

---

## 💡 Key Points

- ✅ Substring matching should be **case-insensitive**
- ✅ Maintain the **original box structure** (same number of boxes)
- ✅ Empty boxes should be preserved as empty arrays `[]`
- ✅ An item matches if it contains **any** city name as a substring

---

## 📝 Example Scenario

Imagine you're moving westward and want to keep only items related to cities on your route:

```javascript
const cities = ["Denver", "Vegas", "Phoenix"];
const boxes = [
  ["Denver Broncos Jersey", "Random Book", "Vegas Dice"],
  ["Phoenix Poster", "Coffee Mug"],
  ["Laptop", "Phoenix T-shirt", "Denver Map"]
];

// Expected output:
[
  ["Denver Broncos Jersey", "Vegas Dice"],
  ["Phoenix Poster"],
  ["Phoenix T-shirt", "Denver Map"]
]
```

---

## 🚀 Getting Started

Start by considering:
- How to perform case-insensitive substring matching
- How to preserve the box structure even when boxes become empty
- Efficient ways to check multiple city names against each item

Good luck! 🎉
