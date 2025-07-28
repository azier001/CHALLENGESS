# 🔍 Find Your Lost Item in the City

## 📊 Challenge Overview

| Attribute | Details |
|-----------|---------|
| **Difficulty** | `Easy` |
| **Function Name** | `findLostItem` |
| **Category** | Array Searching |

---

## 🎯 Problem Description

Create a function that helps locate a lost item from your daily essentials. This function simulates the common scenario of searching through your belongings to find a specific item you've misplaced.

The function should efficiently search through an array of items and provide clear feedback about whether the target item exists in your collection.

---

## 📝 Function Specification

### Function Signature
```javascript
function findLostItem(items, searchItem)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `items` | `Array<string>` | List of items the person typically carries |
| `searchItem` | `string` | The specific item they are trying to find |

### Return Value

| Condition | Return Value |
|-----------|--------------|
| Item found | `"Item found!"` |
| Item not found | `"Item not found!"` |

---

## 🛠️ Implementation Requirements

### Core Logic
1. **Array Traversal**: Use an array method or loop through the `items` array
2. **Item Comparison**: Check if the `searchItem` exists in the `items` array
3. **Conditional Return**: 
   - If found → return `"Item found!"`
   - If not found → return `"Item not found!"`

### Suggested Approaches
- ✅ Use `Array.includes()` method
- ✅ Use `Array.indexOf()` method
- ✅ Use `for` loop with manual comparison
- ✅ Use `Array.find()` method

---

## 💡 Example Usage

```javascript
// Example test cases
const dailyItems = ["wallet", "keys", "phone", "sunglasses", "notebook"];

console.log(findLostItem(dailyItems, "keys"));        // "Item found!"
console.log(findLostItem(dailyItems, "headphones"));  // "Item not found!"
console.log(findLostItem(dailyItems, "wallet"));      // "Item found!"
```

---

## 🧪 Test Scenarios

| Test Case | Input Items | Search Item | Expected Output |
|-----------|-------------|-------------|-----------------|
| Found item | `["book", "pen", "laptop"]` | `"pen"` | `"Item found!"` |
| Not found | `["book", "pen", "laptop"]` | `"mouse"` | `"Item not found!"` |
| Empty array | `[]` | `"phone"` | `"Item not found!"` |
| Case sensitive | `["Phone"]` | `"phone"` | `"Item not found!"` |

---

## 🎯 Learning Objectives

- 📚 **Array Methods**: Practice using built-in array methods for searching
- 🔄 **Loops**: Understand iteration patterns for data searching
- 🎭 **Conditional Logic**: Implement branching logic based on search results
- 📤 **Return Statements**: Practice returning appropriate string messages

---

## ⚡ Performance Notes

- Time Complexity: `O(n)` where n is the length of the items array
- Space Complexity: `O(1)` constant space usage
- Most efficient approach: `Array.includes()` method

---

## 🚀 Extension Ideas

Once you've mastered the basic implementation, consider these enhancements:

- 🔤 **Case-insensitive search**
- 🔍 **Partial string matching**
- 📊 **Return item index when found**
- 📝 **Multiple item search support**
