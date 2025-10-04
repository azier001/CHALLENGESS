# 🔮 Fortune Teller Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that predicts whether a target number is lucky or unlucky based on an array of numbers.

---

## 🎯 Objective

Implement a function named `fortuneTeller` that:
- Accepts an **array of numbers** and a **target number**
- Processes the array using specific rules
- Returns a fortune prediction based on the result

---

## 📝 Requirements

### Function Signature
```javascript
fortuneTeller(array, target)
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `array` | `Array<number>` | An array of numbers to process |
| `target` | `number` | The target number to compare against |

### Return Value
| Value | Type | Condition |
|-------|------|-----------|
| `"Lucky!"` | `string` | When sum equals target |
| `"Unlucky!"` | `string` | When sum does not equal target |

---

## ⚙️ Algorithm Steps

Follow these steps to implement the solution:

1. **Initialize** a variable `sum` to `0`

2. **Loop** through each number in the array

3. **For each number:**
   - ✅ If the number is **even** → **add** it to `sum`
   - ❌ If the number is **odd** → **subtract** it from `sum`

4. **After the loop:**
   - Compare `sum` with `target`
   - Return `"Lucky!"` if they are equal
   - Return `"Unlucky!"` if they are not equal

---

## 📌 Important Notes

> **Empty Array:** If the input array is empty, consider the sum to be `0`.

> **Target Number:** The target can be any integer (positive, negative, or zero).

---

## 💡 Examples

### Example 1: Lucky Prediction
```javascript
fortuneTeller([2, 3, 4, 5], 2)
// Process: 2 (even) + (-3) (odd) + 4 (even) + (-5) (odd) = -2
// Expected: "Unlucky!"
```

### Example 2: Empty Array
```javascript
fortuneTeller([], 0)
// Process: sum = 0
// Expected: "Lucky!"
```

### Example 3: All Even Numbers
```javascript
fortuneTeller([2, 4, 6, 8], 20)
// Process: 2 + 4 + 6 + 8 = 20
// Expected: "Lucky!"
```

---

## 🏆 Success Criteria

Your solution should:
- ✓ Handle empty arrays correctly
- ✓ Process even numbers by addition
- ✓ Process odd numbers by subtraction
- ✓ Return the correct string format
- ✓ Work with positive, negative, and zero targets

---

**Good luck with your fortune telling! 🍀**
