# 🔢 Find Prism Numbers in Range

## Challenge Level
**Easy** ⭐

---

## 📋 Description

Create a function named `findPrismNumbers` that receives two numbers, `start` and `end`. The function will find all the **prism numbers** between `start` and `end` (inclusive) and return them as an array.

---

## 🎯 What is a Prism Number?

A **prism number** is a number that is the product of two consecutive numbers.

### Mathematical Definition

A number `n` is a prism number if:
```
n = k × (k + 1)
```
where `k` is a positive integer.

---

## 💡 Examples

Here are some examples of prism numbers:

| Prism Number | Calculation | Consecutive Numbers |
|--------------|-------------|---------------------|
| 2            | 1 × 2       | 1 and 2             |
| 6            | 2 × 3       | 2 and 3             |
| 12           | 3 × 4       | 3 and 4             |
| 20           | 4 × 5       | 4 and 5             |
| 30           | 5 × 6       | 5 and 6             |
| 42           | 6 × 7       | 6 and 7             |
| 56           | 7 × 8       | 7 and 8             |

### Detailed Examples

✅ **6 is a prism number** because it is the product of 2 and 3.

✅ **30 is a prism number** because it is the product of 5 and 6.

---

## 📝 Function Signature

```javascript
function findPrismNumbers(start, end) {
    // Your implementation here
}
```

### Parameters

- **`start`** (Number): The starting number of the range (inclusive)
- **`end`** (Number): The ending number of the range (inclusive)

### Return Value

- **Array**: An array containing all prism numbers found within the specified range

---

## 🧪 Test Cases

```javascript
// Example 1
findPrismNumbers(1, 10);
// Expected Output: [2, 6]

// Example 2
findPrismNumbers(5, 30);
// Expected Output: [6, 12, 20, 30]

// Example 3
findPrismNumbers(10, 50);
// Expected Output: [12, 20, 30, 42]
```

---

## 💭 Hints

1. Consider iterating through consecutive number pairs
2. Check if the product falls within the given range
3. You can calculate the maximum value of `k` needed based on the `end` value
4. Remember to include both `start` and `end` in your range check

---

## ⚡ Challenge

Try to implement this function efficiently! Think about:
- How to minimize unnecessary calculations
- How to handle edge cases (e.g., when `start` > `end`)
- Different approaches to solve this problem

---

**Good luck! Happy coding! 🚀**
