# 🧺 Picnic Basket Inventory Challenge

## 📋 Challenge Overview
**Difficulty Level:** `Easy` 🟢  
**Topic:** String Manipulation & Loops  
**Estimated Time:** 10-15 minutes

---

## 🎯 What You'll Learn
- Working with string concatenation
- Using loops to generate sequential data
- Function parameter handling
- String formatting and separation

---

## 📝 Problem Description

Imagine you're organizing a picnic and need to keep track of items in your basket! You already have some items, but you want to add more items with systematic naming.

Your task is to create a function called `preparePicnicBasket` that:
- Takes your current basket items
- Adds a specified number of new items
- Returns a complete inventory list

---

## 🔧 Function Specifications

### Function Signature
```javascript
function preparePicnicBasket(currentItems, itemsToAdd)
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `currentItems` | `string` | Items currently in the basket, separated by `", "` |
| `itemsToAdd` | `number` | Number of additional items to add to the basket |

### Return Value
- **Type:** `string`
- **Format:** All items separated by `", "` (comma + space)

---

## 🎯 Requirements Checklist

- [ ] Create a function named `preparePicnicBasket`
- [ ] Accept two parameters: `currentItems` and `itemsToAdd`
- [ ] Use a **loop** to generate new items
- [ ] New items should follow the pattern: `"item1"`, `"item2"`, `"item3"`, etc.
- [ ] Combine current items with new items
- [ ] Return everything as a single string with proper comma-space separation

---

## 💡 Example Walkthrough

### 📥 Input
```javascript
currentItems = "apple, banana, sandwich"
itemsToAdd = 3
```

### 🔄 Process
1. Start with existing items: `"apple, banana, sandwich"`
2. Add `item1` → `"apple, banana, sandwich, item1"`
3. Add `item2` → `"apple, banana, sandwich, item1, item2"`
4. Add `item3` → `"apple, banana, sandwich, item1, item2, item3"`

### 📤 Expected Output
```javascript
"apple, banana, sandwich, item1, item2, item3"
```

---

## 🧪 Test Cases

### Test Case 1: Basic Addition
```javascript
Input: currentItems = "water, chips", itemsToAdd = 2
Expected: "water, chips, item1, item2"
```

### Test Case 2: Empty Basket
```javascript
Input: currentItems = "", itemsToAdd = 3
Expected: "item1, item2, item3"
```

### Test Case 3: No New Items
```javascript
Input: currentItems = "apple, orange", itemsToAdd = 0
Expected: "apple, orange"
```

---

## 🛠️ Implementation Hints

### For Beginners:
1. **Start Simple:** First, figure out how to combine two strings
2. **Use a Loop:** Think about `for` loops - they're perfect for counting!
3. **String Building:** Consider how to build your result string step by step
4. **Edge Cases:** What happens if `itemsToAdd` is 0? What if `currentItems` is empty?

### Key Concepts to Remember:
- **String Concatenation:** Joining strings together
- **Loop Iteration:** Repeating code a specific number of times
- **Template Literals:** Using backticks for dynamic strings (optional but helpful)

---

## 🎨 Code Structure Template

```javascript
function preparePicnicBasket(currentItems, itemsToAdd) {
    // Your code here
    // 1. Handle the current items
    // 2. Use a loop to add new items
    // 3. Return the complete basket inventory
}
```

---

## 🏆 Success Criteria

Your solution should:
- ✅ Pass all test cases
- ✅ Use a loop structure
- ✅ Handle edge cases gracefully
- ✅ Return properly formatted strings
- ✅ Follow the exact naming convention for new items

---

## 🚀 Ready to Code?

Now that you understand the requirements, it's time to implement your solution! Remember to test your function with different inputs to make sure it works correctly.

Good luck with your picnic basket inventory system! 🎉
