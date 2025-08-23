# 🔢 Decimal to Binary Conversion

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function that converts decimal numbers to their binary representation. This fundamental programming exercise helps you understand number base conversions and bitwise operations.

---

## 🎯 Objective

Design a function named `decimalToBinary` that takes a positive integer in base 10 and returns its binary equivalent as a string.

---

## 📝 Function Specification

### Function Signature
```javascript
function decimalToBinary(number) {
    // Your implementation here
}
```

### Parameters
- **`number`** *(integer)*: A positive integer in decimal format

### Return Value
- **Type:** `string`
- **Content:** Binary representation of the input number

---

## 🔧 Requirements

✅ **Input Constraints:**
- The input `number` will always be a positive integer
- No need to handle negative numbers or zero

✅ **Output Format:**
- Return the binary equivalent as a string
- No leading zeros required (except for the number 0 itself)

✅ **Algorithm Approach:**
- Repeatedly divide the number by 2
- Keep track of the remainders
- The remainders in reverse order form the binary equivalent

---

## 💡 Algorithm Explanation

### Step-by-Step Process:

1. **Initialize** an empty result container
2. **Divide** the decimal number by 2
3. **Record** the remainder (0 or 1)
4. **Update** the number to the quotient
5. **Repeat** steps 2-4 until the number becomes 0
6. **Reverse** the collected remainders to get the binary result

### Visual Example:
```
Converting 13 to binary:
13 ÷ 2 = 6 remainder 1
6 ÷ 2 = 3 remainder 0
3 ÷ 2 = 1 remainder 1
1 ÷ 2 = 0 remainder 1

Reading remainders from bottom to top: 1101
```

---

## 🧪 Test Cases

| Input | Expected Output | Description |
|-------|----------------|-------------|
| `1` | `"1"` | Smallest positive integer |
| `2` | `"10"` | First power of 2 |
| `8` | `"1000"` | Power of 2 |
| `13` | `"1101"` | Mixed binary digits |
| `255` | `"11111111"` | 8-bit maximum |

---

## 🚀 Getting Started

Ready to implement your solution? Remember to:

- Handle the division and remainder operations correctly
- Build the binary string in the proper order
- Test with various input values
- Consider edge cases like powers of 2

**Good luck coding!** 🎉
