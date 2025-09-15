# 🏠 Organize Your Home Office Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Transform your cluttered home office into an organized workspace! Your mission is to create a function that categorizes various office items, helping improve productivity through better organization.

---

## 🎯 Objective

Create a function named `organizeWorkspace` that takes an array of office items and sorts them into three distinct categories: **Electronics**, **Stationery**, and **Books**.

---

## 📝 Function Specification

### Function Signature
```javascript
function organizeWorkspace(items)
```

### Parameters
- **`items`** *(array)*: An array of strings representing office items
  - Can contain any number of items (including zero)
  - Each string represents a single office item

### Return Value
Returns a **2D array** with exactly three subarrays:
1. **First subarray**: All electronic items
2. **Second subarray**: All stationery items  
3. **Third subarray**: All book-related items

---

## 📂 Item Categories

### ⚡ Electronics
Items that require power or are technological devices:
- `laptop`
- `phone` 
- `tablet`
- `computer`
- `mouse`
- `keyboard`
- `monitor`
- `printer`
- `scanner`
- `charger`

### ✏️ Stationery
Traditional office supplies for writing and organizing:
- `pen`
- `pencil`
- `notebook`
- `paper`
- `stapler`
- `scissors`
- `tape`
- `glue`
- `ruler`
- `eraser`

### 📚 Books
Reading materials and reference documents:
- `book`
- `magazine`
- `journal`
- `kindle`
- `textbook`
- `novel`
- `dictionary`
- `encyclopedia`
- `manual`
- `guide`

---

## ⚠️ Important Notes

> **Unrecognized Items**: If an item doesn't belong to any of the three categories above, it should be **ignored** and not included in the result.

---

## 💡 Example Usage

```javascript
// Example input
const officeItems = ["laptop", "pen", "book", "mouse", "scissors", "magazine"];

// Expected output
const result = organizeWorkspace(officeItems);
// Result: [["laptop", "mouse"], ["pen", "scissors"], ["book", "magazine"]]
```

---

## 🎯 Success Criteria

✅ Function correctly categorizes all recognized items  
✅ Returns exactly three subarrays in the correct order  
✅ Ignores unrecognized items  
✅ Handles empty arrays gracefully  
✅ Maintains original item names (case-sensitive)

---

*Happy organizing! 🎉*
