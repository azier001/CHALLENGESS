# 🫐 Counting Brierberries

## Challenge Level
**Easy** ⭐

---

## 📋 Problem Description

Create a function named `countBrierberries` that receives an array of numbers called `bushes`. Each number represents the number of brierberries on a bush.

### 🎯 Objective

Calculate the **total number of brierberries** picked from the bushes.

### ⚠️ Special Rule

**If a bush has more than 10 brierberries, stop picking immediately and return the total count.**

---

## 📝 Function Signature

```javascript
function countBrierberries(bushes)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `bushes` | `Array<number>` | An array where each element represents the number of brierberries on a bush |

### Returns

- **Type:** `number`
- **Description:** The total count of brierberries picked before encountering a bush with more than 10 berries

---

## 🔒 Constraints

- ✅ The input array will **always contain at least one element**
- ✅ All elements in the input array will be **non-negative integers**

---

## 💡 Examples

### Example 1: Normal Case
```javascript
countBrierberries([3, 5, 2, 7])
// Output: 17
// Explanation: 3 + 5 + 2 + 7 = 17 (all bushes have ≤ 10 berries)
```

### Example 2: Stop Early
```javascript
countBrierberries([4, 6, 15, 3, 2])
// Output: 10
// Explanation: 4 + 6 = 10, then stop (next bush has 15 > 10)
```

### Example 3: First Bush Exceeds Limit
```javascript
countBrierberries([12, 5, 3])
// Output: 0
// Explanation: First bush has 12 > 10, so stop immediately
```

### Example 4: Exactly 10 Berries
```javascript
countBrierberries([10, 5, 3])
// Output: 18
// Explanation: 10 + 5 + 3 = 18 (10 is not greater than 10, so continue)
```

---

## 🎓 Key Concepts

This challenge tests your understanding of:

- 🔄 **Array iteration** with early termination
- 🔢 **Accumulator patterns** for summing values
- ✋ **Conditional logic** for breaking loops
- 📊 **Edge case handling**

---

## 💭 Hints

<details>
<summary>Click to reveal hints</summary>

1. You'll need to iterate through the array sequentially
2. Keep a running total of berries collected
3. Check each bush's berry count before adding it to your total
4. Remember: if a bush has **more than 10** (not equal to 10), stop immediately
5. Consider using a `for` loop with a `break` statement, or a `while` loop

</details>

---

**Happy Coding!** 🚀
