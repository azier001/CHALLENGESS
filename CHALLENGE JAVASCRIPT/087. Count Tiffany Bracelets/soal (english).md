# 💎 Count Tiffany Bracelets

## 🏷️ Challenge Information
- **Difficulty Level:** `Easy`
- **Challenge Type:** Binary Manipulation
- **Skills:** Number conversion, Binary operations, Loops

---

## 📋 Problem Description

Create a function named `countTiffanyBracelets` that processes the number of bracelets in a jewelry store using binary representation.

### 🎯 Objective
Your task is to count the number of `1` digits in the binary representation of a given number.

---

## ⚙️ Function Requirements

### Function Signature
```javascript
function countTiffanyBracelets(num)
```

### Parameters
- **`num`** *(number)*: Represents the number of bracelets in the store

### Process Flow
The function should follow these steps:

1. **🔄 Convert** the input number to binary representation
2. **🔢 Initialize** a counter variable to `0`
3. **🔍 Loop** through each digit in the binary string
4. **➕ Increment** the counter by `1` if the current digit is `'1'`
5. **📤 Return** the final counter value

---

## 💡 Algorithm Breakdown

```
Input: num (integer)
│
├─ Step 1: Convert num to binary string
├─ Step 2: counter = 0
├─ Step 3: For each digit in binary string:
│           │
│           └─ If digit == '1':
│               └─ counter++
│
└─ Step 4: Return counter
```

---

## 🧮 Example Walkthrough

Let's trace through an example:

**Input:** `num = 13`

1. **Binary conversion:** `13` → `"1101"`
2. **Initialize counter:** `counter = 0`
3. **Loop through digits:**
   - `'1'` → counter becomes `1`
   - `'1'` → counter becomes `2`  
   - `'0'` → counter stays `2`
   - `'1'` → counter becomes `3`
4. **Result:** `3`

---

## 📊 Test Cases

| Input | Binary | Expected Output | Description |
|-------|--------|----------------|-------------|
| `0`   | `"0"`  | `0`            | No set bits |
| `1`   | `"1"`  | `1`            | Single set bit |
| `7`   | `"111"`| `3`            | All bits set |
| `8`   | `"1000"`| `1`           | Power of 2 |
| `15`  | `"1111"`| `4`           | All bits in nibble |

---

## 🏆 Success Criteria

- ✅ Function correctly converts number to binary
- ✅ Properly counts '1' digits
- ✅ Returns accurate count
- ✅ Handles edge cases (0, powers of 2)
- ✅ Efficient implementation

---

## 💭 Hints

> 🔍 **Hint 1:** JavaScript's `toString(2)` method can convert numbers to binary  
> 🔍 **Hint 2:** You can iterate through a string just like an array  
> 🔍 **Hint 3:** Remember to convert string digits to numbers when comparing
