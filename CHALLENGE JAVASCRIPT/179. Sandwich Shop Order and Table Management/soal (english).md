# 🥪 Sandwich Shop Order and Table Management

## 📋 Challenge Overview

**Difficulty Level:** `Medium`

Your neighborhood sandwich shop needs to track pending orders and manage seating efficiently during busy lunch hours. Help them streamline their operations by creating a management system!

---

## 🎯 Objective

Write a function `processShopOrders` that takes `orders` and `tableStatuses` as inputs and returns an object containing:
- Sandwich counts for all pending orders
- Available tables for new customers

---

## 🧠 Logic Requirements

Your solution should accomplish the following:

1. **Count Sandwich Orders**  
   Count how many times each sandwich type appears in the pending orders list

2. **Identify Available Tables**  
   Determine which tables are currently available for new customers

3. **Generate Management Summary**  
   Combine both pieces of information into a single, easy-to-read report

---

## ⚙️ Conditions & Rules

- ✅ Only count tables with status `"available"` as free
- 📊 Table statuses can be one of three values:
  - `"available"` - Ready for new customers
  - `"occupied"` - Currently in use
  - `"reserved"` - Booked for future customers
- 🔢 Include sandwich types in the count even if the count is `0`

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `orders` | `array` | Array of sandwich names currently being prepared |
| `tableStatuses` | `array` | Array of table status strings |

---

## 📤 Return Value

**Type:** `Object`

**Format:**
```json
{
  "sandwichCounts": {
    "BLT": 2,
    "Club": 1
  },
  "availableTables": [1, 3]
}
```

### Structure Breakdown:

- **`sandwichCounts`** (Object)  
  Key-value pairs where keys are sandwich names and values are their counts

- **`availableTables`** (Array)  
  List of table indices (0-based) that have `"available"` status

---

## 💡 Example Usage

```javascript
const orders = ["BLT", "Club", "BLT", "Veggie"];
const tableStatuses = ["occupied", "available", "reserved", "available"];

const result = processShopOrders(orders, tableStatuses);
console.log(result);
// Output:
// {
//   sandwichCounts: { BLT: 2, Club: 1, Veggie: 1 },
//   availableTables: [1, 3]
// }
```

---

## 🚀 Getting Started

Ready to tackle this challenge? Start by:

1. Setting up your function signature
2. Creating a structure to count sandwiches
3. Filtering through table statuses to find available ones
4. Combining the results into the required format

Good luck! 🎉
