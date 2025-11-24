# 🌿 Garden Center Inventory Analysis

## Challenge Level
**Medium** 🟡

---

## 📋 Overview

Write a function `analyzeGardenInventory` that processes plant and supply records to generate a comprehensive inventory analysis for a community garden center.

The function should identify specialty plants, flag inventory issues, and calculate total inventory values.

---

## 🎯 Objective

Create a function that analyzes plant and supply data to provide:
- Identification of specialty plant varieties
- Inventory status alerts (low stock and high cost items)
- Total inventory value calculation
- Statistical summary of flagged items

---

## 🔧 Function Signature

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords)
```

---

## 📥 Parameters

### `plantRecords` (Array)
An array of objects representing plant inventory.

**Structure:**
- `name` (string) - The plant variety name
- `count` (number) - The quantity in stock

**Example:**
```javascript
[
  { name: "Helichrysum Silver", count: 12 },
  { name: "Acanthus Mollis", count: 8 },
  { name: "Lavender", count: 25 }
]
```

### `supplyRecords` (Array)
An array of objects representing gardening supplies.

**Structure:**
- `item` (string) - The supply item name
- `qty` (number) - The quantity available
- `price` (number) - The price per unit

**Example:**
```javascript
[
  { item: "Fertilizer", qty: 3, price: 25 },
  { item: "Garden Hose", qty: 10, price: 75 },
  { item: "Pruning Shears", qty: 15, price: 30 }
]
```

---

## 📤 Return Value

Returns an **object** containing the inventory analysis results.

**Structure:**
```javascript
{
  specialtyPlants: number,
  lowStockItems: number,
  highCostItems: number,
  totalValue: number
}
```

### Properties Explained

| Property | Type | Description |
|----------|------|-------------|
| `specialtyPlants` | number | Count of plants containing "Helichrysum" or "Acanthus" |
| `lowStockItems` | number | Count of supplies with quantity ≤ 5 |
| `highCostItems` | number | Count of supplies with price > 50 |
| `totalValue` | number | Sum of all supply values (qty × price) |

---

## 🧮 Logic Requirements

### 1. **Specialty Plant Identification**
- Search plant names for varieties containing `"Helichrysum"` or `"Acanthus"`
- Match should be **case-insensitive**
- Count all matching plants

### 2. **Low Stock Detection**
- Flag supplies where `qty ≤ 5`
- Count all flagged items

### 3. **High Cost Detection**
- Flag supplies where `price > 50`
- Count all flagged items

### 4. **Total Value Calculation**
- For each supply: calculate `qty × price`
- Sum all values to get total inventory value

---

## 💡 Example Usage

```javascript
const plants = [
  { name: "Helichrysum Italicum", count: 15 },
  { name: "Acanthus Spinosus", count: 7 },
  { name: "Rose Bush", count: 20 },
  { name: "helichrysum bracteatum", count: 10 }
];

const supplies = [
  { item: "Premium Soil", qty: 3, price: 40 },
  { item: "Watering Can", qty: 8, price: 65 },
  { item: "Hand Trowel", qty: 2, price: 15 },
  { item: "Garden Gloves", qty: 20, price: 12 }
];

const result = analyzeGardenInventory(plants, supplies);

console.log(result);
// Output:
// {
//   specialtyPlants: 3,
//   lowStockItems: 2,
//   highCostItems: 1,
//   totalValue: 1070
// }
```

---

## ✅ Key Points to Remember

- ✨ Specialty plant detection is **case-insensitive**
- ⚠️ Low stock threshold is **≤ 5** (inclusive)
- 💰 High cost threshold is **> 50** (exclusive)
- 🧾 Total value includes **all supplies**, not just flagged ones
- 📊 A supply can be both low-stock **and** high-cost

---

## 🎓 Skills Tested

- Array manipulation and iteration
- Object property access
- String matching (case-insensitive)
- Conditional logic
- Mathematical calculations
- Data aggregation

---

**Good luck with your implementation! 🌱**
