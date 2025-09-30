# 🕯️ Banquet Binary Candles

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that determines how many candles need to be lit to represent a decimal number in binary format.

---

## 🎯 Objective

Implement a function named `banquetBinaryCandles` that calculates the number of lit candles required to display a given decimal number in its binary representation.

---

## 💡 Concept

In binary representation:
- **`1`** represents a **lit candle** 🕯️
- **`0`** represents an **unlit candle**

The challenge is to count how many `1`s appear in the binary form of a decimal number.

### Example

```
Decimal: 13
Binary:  1101
Lit Candles: 3 (three '1's)
```

---

## 🔧 Function Specification

### Function Name
```javascript
banquetBinaryCandles(decimalCandles)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `decimalCandles` | `number` | The decimal number to be converted to binary format |

### Return Value

- **Type:** `number` (integer)
- **Description:** The count of lit candles (number of `1`s in binary representation)

---

## 📝 Implementation Steps

1. **Convert** the decimal number to binary format
2. **Count** the number of `1`s in the binary representation
3. **Return** the count as the result

---

## 🧪 Test Cases

| Decimal Input | Binary | Lit Candles | Expected Output |
|---------------|--------|-------------|-----------------|
| 0 | 0 | 0 | `0` |
| 1 | 1 | 1 | `1` |
| 7 | 111 | 3 | `3` |
| 8 | 1000 | 1 | `1` |
| 15 | 1111 | 4 | `4` |
| 13 | 1101 | 3 | `3` |

---

## 💻 Example Usage

```javascript
banquetBinaryCandles(13);  // Returns: 3
banquetBinaryCandles(7);   // Returns: 3
banquetBinaryCandles(8);   // Returns: 1
banquetBinaryCandles(0);   // Returns: 0
```

---

## 🔑 Key Points

- ✅ The function should handle any non-negative integer
- ✅ Binary conversion is the core operation
- ✅ Counting `1`s is equivalent to counting set bits
- ✅ Return value must be an integer

---

## 🚀 Hints

- Consider using JavaScript's built-in `toString(2)` method for binary conversion
- String methods can help count occurrences of `'1'`
- Alternatively, explore bitwise operations for an optimized solution

---

**Good luck with your implementation! 🎉**
