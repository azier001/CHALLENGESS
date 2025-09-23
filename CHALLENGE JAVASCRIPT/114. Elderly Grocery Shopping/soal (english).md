# 🛒 Elderly Grocery Shopping Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy` ⭐

### 🎯 Objective
Create a function named `groceryBasket` that helps an elderly person determine which items they can actually purchase from a taximan's makeshift store based on item availability.

---

## 🔧 Function Specification

### Function Name
```javascript
groceryBasket(storeItems, wantedItems)
```

### 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `storeItems` | `Array<string>` | Items available in the taximan's makeshift store |
| `wantedItems` | `Array<string>` | Items the elderly person wants to buy |

### 📤 Return Value
- **Type:** `Array<string>`
- **Description:** Items the elderly person can actually purchase (intersection of wanted and available items)

---

## 💡 Problem Description

An elderly person is shopping at a taximan's makeshift store and needs help determining which items from their shopping list are actually available for purchase. 

Your function should:
- ✅ Compare wanted items with store inventory
- ✅ Return only items that are both wanted AND available
- ✅ Handle edge cases (no matches, all matches)

---

## 📝 Example Usage

```javascript
// Store inventory
let storeItems = ['bread', 'milk', 'eggs', 'soap', 'toothpaste'];

// Customer's shopping list
let wantedItems = ['bread', 'eggs', 'coffee', 'medicine'];

// Function call
let purchasedItems = groceryBasket(storeItems, wantedItems);

// Expected output
console.log(purchasedItems); 
// Output: ['bread', 'eggs']
```

### 🔍 Example Breakdown

| Item | Available in Store | Wanted by Customer | Can Purchase |
|------|-------------------|-------------------|--------------|
| `bread` | ✅ | ✅ | ✅ |
| `eggs` | ✅ | ✅ | ✅ |
| `coffee` | ❌ | ✅ | ❌ |
| `medicine` | ❌ | ✅ | ❌ |

**Result:** Only `['bread', 'eggs']` can be purchased.

---

## 🎯 Test Scenarios

### Scenario 1: Partial Match
```javascript
storeItems = ['apple', 'banana', 'orange'];
wantedItems = ['apple', 'grape', 'banana'];
// Expected: ['apple', 'banana']
```

### Scenario 2: No Match
```javascript
storeItems = ['tea', 'sugar', 'rice'];
wantedItems = ['coffee', 'honey', 'bread'];
// Expected: []
```

### Scenario 3: Complete Match
```javascript
storeItems = ['water', 'juice', 'soda'];
wantedItems = ['water', 'juice'];
// Expected: ['water', 'juice']
```

---

## ⚠️ Important Considerations

- 🔄 Handle empty arrays gracefully
- 📝 Maintain original order from `wantedItems`
- 🎯 Ensure exact string matching (case-sensitive)
- ⚡ Consider performance for larger datasets

---

## 🏆 Success Criteria

Your solution should correctly handle all edge cases and return the intersection of the two input arrays while preserving the order of items as they appear in the `wantedItems` array.
