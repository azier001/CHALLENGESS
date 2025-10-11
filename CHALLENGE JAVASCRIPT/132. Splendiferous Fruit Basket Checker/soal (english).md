# 🍎 Splendiferous Fruit Basket Checker

## Challenge Overview

**Difficulty Level:** `Easy`

Create a function that determines whether a fruit basket qualifies as "splendiferous" based on specific validation criteria.

---

## 📋 Challenge Description

Your task is to create a function named `fruitBasketChecker` that validates fruit baskets according to specific rules. The function must check multiple conditions to determine if a basket meets the "splendiferous" standard.

---

## ✨ What Makes a Basket Splendiferous?

A fruit basket is considered **splendiferous** when **ALL** of the following conditions are met:

1. ✅ **Valid Fruit Name**  
   The fruit name must contain only letters and spaces (no numbers or special characters)

2. 🧃 **Juicy Fruit**  
   The fruit must be one of the following juicy varieties:
   - Apple
   - Orange
   - Pear
   - Peach
   - Watermelon

3. 🔢 **Valid Quantity**  
   The quantity must be between **1 and 100** (inclusive)

---

## 🛠️ Implementation Steps

Follow these steps to build your solution:

| Step | Action | Description |
|------|--------|-------------|
| 1 | **Validate Name** | Use a regular expression to check if the fruit name contains only letters and spaces |
| 2 | **Normalize Input** | Convert the fruit name to lowercase for easier comparison |
| 3 | **Check Juiciness** | Verify if the fruit is in the list of juicy fruits |
| 4 | **Validate Quantity** | Ensure the quantity falls within the valid range (1-100) |
| 5 | **Combine Conditions** | Use logical operators to check if all conditions are met |
| 6 | **Return Result** | Return the appropriate message based on the validation result |

---

## 📥 Function Parameters

### `fruitBasketChecker(fruitName, quantity)`

| Parameter | Type | Description |
|-----------|------|-------------|
| `fruitName` | `string` | The name of the fruit to be checked |
| `quantity` | `number` | The quantity of fruit in the basket |

---

## 📤 Return Value

The function should return a **string message** indicating whether the fruit basket is splendiferous or not.

> **Note:** The exact message format should be determined based on the validation result.

---

## 💡 Hints

- Regular expressions can help validate string patterns
- Array methods can check if a value exists in a list
- Comparison operators can validate numeric ranges
- Logical AND (`&&`) ensures all conditions are true

---

## 🎯 Example Usage

```javascript
fruitBasketChecker("Apple", 50)
// Should check: valid name ✓, juicy fruit ✓, valid quantity ✓

fruitBasketChecker("Banana", 10)
// Should fail: not a juicy fruit ✗

fruitBasketChecker("Orange123", 20)
// Should fail: invalid name (contains numbers) ✗

fruitBasketChecker("Watermelon", 150)
// Should fail: quantity exceeds maximum ✗
```

---

## 🏁 Getting Started

Begin by defining your function structure and implementing each validation step systematically. Remember to test your function with various inputs to ensure all conditions work correctly!

```javascript
function fruitBasketChecker(fruitName, quantity) {
  // Your implementation here
}
```

Good luck! 🍊🍑🍐
