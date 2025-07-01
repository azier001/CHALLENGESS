# 🔢 Count Special Numbers in Range

## 📋 Challenge Overview

| **Difficulty** | **Type** | **Focus Area** |
|---------------|----------|----------------|
| 🟢 **Easy** | Algorithm | Loop Control & Conditionals |

---

## 🎯 Objective

Create a function named `countSpecialNumbers` that counts and returns the number of **special numbers** within a given range (inclusive).

---

## 🔍 Special Number Definition

A number is considered **special** if it meets **BOTH** of the following criteria:

### ✅ Criteria 1: Divisibility
- The number must be divisible by **3** OR **5**

### ✅ Criteria 2: Digit Constraint
- The number must **NOT** contain the digit **7**

---

## 📝 Function Specification

### Function Signature
```javascript
function countSpecialNumbers(start, end)
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `start` | `number` | The beginning of the range *(inclusive)* |
| `end` | `number` | The end of the range *(inclusive)* |

### Return Value
- **Type**: `number` (integer)
- **Description**: Count of special numbers in the specified range

---

## 🛠️ Implementation Requirements

### Mandatory Elements
- ✅ Use `break` and `continue` statements for loop control
- ✅ Function must be between **10-19 lines of code**
- ✅ Implement efficient flow control to improve performance

### Suggested Approach
1. **Initialize** a counter for special numbers
2. **Loop** through numbers from `start` to `end` (inclusive)
3. **Check divisibility** by 3 or 5 → use `continue` if not divisible
4. **Check for digit 7** → use `continue` if contains digit 7
5. **Increment counter** if number passes both checks
6. **Return** the final counter value

---

## 💡 Key Concepts

### Loop Control Statements
- **`continue`**: Skip the current iteration and move to the next
- **`break`**: Exit the loop entirely (if needed)

### Efficiency Tips
- Use `continue` to skip unnecessary checks
- Order conditions from most likely to fail to least likely

---

## 📊 Example Range Analysis

### Sample Range: 10-20
Let's analyze which numbers would be special:

| Number | Divisible by 3 or 5? | Contains 7? | Special? |
|--------|---------------------|-------------|----------|
| 10 | ✅ (÷5) | ❌ | ✅ **YES** |
| 11 | ❌ | ❌ | ❌ No |
| 12 | ✅ (÷3) | ❌ | ✅ **YES** |
| 13 | ❌ | ❌ | ❌ No |
| 14 | ❌ | ❌ | ❌ No |
| 15 | ✅ (÷3,÷5) | ❌ | ✅ **YES** |
| 16 | ❌ | ❌ | ❌ No |
| 17 | ❌ | ✅ | ❌ No |
| 18 | ✅ (÷3) | ❌ | ✅ **YES** |
| 19 | ❌ | ❌ | ❌ No |
| 20 | ✅ (÷5) | ❌ | ✅ **YES** |

**Result**: 5 special numbers in range 10-20

---

## 🎲 Test Cases to Consider

### Edge Cases
- Range with only one number
- Range where start equals end
- Range with no special numbers
- Range with numbers containing 7
- Negative numbers in range

### Performance Cases
- Large ranges (1-1000)
- Ranges with many multiples of 3 and 5

---

## 🏆 Success Criteria

- ✅ Function correctly identifies special numbers
- ✅ Proper use of `continue` and `break` statements
- ✅ Code is between 10-19 lines
- ✅ Efficient loop control implementation
- ✅ Handles edge cases appropriately

---

## 📚 Learning Outcomes

After completing this challenge, you will have practiced:
- **Loop control** with `break` and `continue`
- **Conditional logic** with multiple criteria
- **String manipulation** for digit checking
- **Algorithm efficiency** optimization
- **Edge case handling**

---

*Good luck with your implementation! 🚀*
