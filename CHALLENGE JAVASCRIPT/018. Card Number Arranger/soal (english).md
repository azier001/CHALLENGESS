
# 🃏 Card Number Arranger

## 🎯 Challenge

**Difficulty:** Easy

You and your friends are making greeting cards on a cozy afternoon.  
You want to arrange the special numbers (like birthdays, anniversaries, or lucky numbers) on the card in a specific pattern.

---

## 📋 Task Description

Create a function named `arrangeCardNumbers` that receives an array of numbers and returns a **new array** with the numbers arranged as follows:

### ✅ Arrangement Rules

1. **Even numbers** must be placed **first**, in **ascending order**
2. **Odd numbers** must come **after**, in **descending order**

---

## 🧾 Function Signature

```javascript
function arrangeCardNumbers(numbers)
```

### 📥 Parameters:

- `numbers` (array):  
  An array of integers representing the special numbers to be arranged on the card.

### 📤 Returns:

- A new array with the numbers arranged according to the specified pattern.

---

## 💡 Example

```javascript
arrangeCardNumbers([3, 2, 8, 5, 7, 4])
// Output: [2, 4, 8, 7, 5, 3]
```



---

## 📝 Notes

- This function can be useful for organizing decorative number patterns for cards, posters, or digital greetings.
- Remember that sorting is case-sensitive to the even/odd classification.

---
