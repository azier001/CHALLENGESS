# 🏷️ Yard Sale Inventory Organizer

## 📋 Challenge Overview

**Difficulty Level:** `Medium`

Create a function that transforms unformatted yard sale item strings into a well-organized inventory summary with categorization and financial calculations.

---

## 🎯 Objective

Write a function called `organizeYardSale` that processes an array of item strings and returns a comprehensive inventory summary object with category-based organization and totals.

---

## 🔧 Function Signature

```javascript
function organizeYardSale(items)
```

---

## 📥 Input Specifications

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `items` | `Array<string>` | Array of item strings in a specific format |

### Item String Format

Each item follows this pattern:

```
"category:name:price"
```

**Example:**
```javascript
[
  "furniture:chair:15.99",
  "kitchen:blender:12.50",
  "furniture:table:30.00"
]
```

---

## 📤 Output Specifications

### Return Value

An object where:
- **Keys** represent item categories
- **Values** are objects containing:
  - `count`: Number of items in the category
  - `total`: Sum of all item prices in the category

### Output Format

```javascript
{
  "category_name": {
    "count": <number>,
    "total": <number>
  }
}
```

### Example Output

```javascript
{
  "furniture": {
    "count": 2,
    "total": 45.99
  },
  "kitchen": {
    "count": 1,
    "total": 12.50
  }
}
```

---

## 🧮 Processing Logic

The function should implement the following steps:

### 1. **Parse Item Strings**
   - Split each string by the `:` delimiter
   - Extract three components: `category`, `name`, and `price`

### 2. **Categorize Items**
   - Group items by their category
   - Increment the count for each item added to a category

### 3. **Calculate Category Totals**
   - Accumulate individual item prices
   - Compute the total price per category

### 4. **Generate Summary**
   - Return an organized object with all categories and their statistics

---

## 💡 Key Requirements

- ✅ Parse all item strings correctly
- ✅ Handle multiple items per category
- ✅ Calculate accurate price totals
- ✅ Maintain proper count of items
- ✅ Return data in the specified format

---

## 🧪 Example Test Case

### Input
```javascript
const items = [
  "furniture:chair:15.99",
  "kitchen:blender:12.50",
  "furniture:table:30.00",
  "electronics:radio:8.00",
  "kitchen:pot:5.50"
];
```

### Expected Output
```javascript
{
  "furniture": {
    "count": 2,
    "total": 45.99
  },
  "kitchen": {
    "count": 2,
    "total": 18.00
  },
  "electronics": {
    "count": 1,
    "total": 8.00
  }
}
```

---

## 🚀 Getting Started

Begin by:
1. Creating the function structure
2. Implementing the string parsing logic
3. Building the category grouping mechanism
4. Adding the calculation logic
5. Testing with various inputs

Good luck! 🎉
