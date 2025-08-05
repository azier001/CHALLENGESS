# 🏠 House Number Converter Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

You are a tourist visiting a beautiful tropical village with thatched-roof huts. The villagers use a unique numbering system for their houses, and they need your help to convert their regular house numbers into their special binary code and arrange them in reverse order.

---

## 🎯 Task Description

Create a function named `houseNumberConverter` that receives `decimalNumbers` as its parameter.

### Function Requirements

Your function should perform the following tasks:

1. **Convert** each decimal house number to its binary representation (as a string)
2. **Reverse** the order of the resulting binary numbers

---

## 📝 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `decimalNumbers` | `array` | An array of integers representing house numbers in decimal format. Each number will be a positive integer. |

---

## 📤 Return Value

The function should return an **array of strings**, where:
- Each string is the binary representation of a house number
- The order of these binary numbers is reversed from the input order

---

## 💡 Example

### Input
```javascript
[5, 12, 3, 7]
```

### Output
```javascript
["111", "11", "1100", "101"]
```

### Step-by-Step Breakdown

| Step | Decimal | Binary | Position |
|------|---------|--------|----------|
| 1 | 5 | "101" | Original: 1st → Final: 4th |
| 2 | 12 | "1100" | Original: 2nd → Final: 3rd |
| 3 | 3 | "11" | Original: 3rd → Final: 2nd |
| 4 | 7 | "111" | Original: 4th → Final: 1st |

**Final Result:** `["111", "11", "1100", "101"]`

---

## 🔧 Implementation Tips

> **Remember:** Handle the conversion and reversal operations separately for clarity.

### Helpful Built-in Methods
- **Binary conversion:** Use JavaScript's built-in methods for converting numbers to binary strings
- **Array manipulation:** Utilize array methods for reversing the order

### Process Flow
```
Input Array → Convert to Binary → Reverse Order → Output Array
```

---

## 🌟 Success Criteria

- ✅ Function correctly converts decimal numbers to binary strings
- ✅ Function reverses the order of the resulting array
- ✅ Function handles positive integers as specified
- ✅ Code is clean and readable with separate operations for conversion and reversal
