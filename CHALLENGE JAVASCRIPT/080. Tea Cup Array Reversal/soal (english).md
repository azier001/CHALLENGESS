# 🍵 Tea Cup Array Reversal Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that reverses the order of tea cups in an array, because sometimes the last cup brewed should be the first one served! ☕

---

## 🎯 Objective

Implement a function named `reverseTeaCupArray` that takes an array of tea types and returns them in reverse order.

## 📝 Function Specification

### Function Name
```javascript
reverseTeaCupArray
```

### Parameters
- **`teaCups`** *(array)*
  - An array of strings
  - Each string represents a type of tea
  - Example: `["Green Tea", "Earl Grey", "Chamomile", "Oolong"]`

### Return Value
- **Type:** Array
- **Description:** A new array containing the same tea cups but in reversed order
- **Example:** `["Oolong", "Chamomile", "Earl Grey", "Green Tea"]`

---

## 💡 Example Usage

```javascript
// Input
const teaCups = ["Green Tea", "Earl Grey", "Chamomile", "Oolong"];

// Function call
const reversedCups = reverseTeaCupArray(teaCups);

// Output
console.log(reversedCups);
// ["Oolong", "Chamomile", "Earl Grey", "Green Tea"]
```

---

## ✅ Requirements Summary

- [ ] Function must be named `reverseTeaCupArray`
- [ ] Must accept one parameter: `teaCups` (array)
- [ ] Must return a **new array** (don't modify the original)
- [ ] Array elements should be in reverse order
- [ ] Handle arrays of any length (including empty arrays)

---

## 🔍 Edge Cases to Consider

| Case | Input | Expected Output |
|------|-------|----------------|
| Empty array | `[]` | `[]` |
| Single element | `["Matcha"]` | `["Matcha"]` |
| Two elements | `["Black Tea", "White Tea"]` | `["White Tea", "Black Tea"]` |

---

## 🌟 Challenge Tips

> **Hint:** JavaScript provides several built-in methods for array manipulation. Consider which method would be most appropriate for reversing an array while keeping the original intact.

**Happy coding! 🚀**
