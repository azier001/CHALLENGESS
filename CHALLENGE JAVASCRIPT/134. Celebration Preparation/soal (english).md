# 🎉 Celebration Preparation Challenge

**Difficulty Level:** Easy

---

## 📋 Challenge Overview

Create a function named `celebrationPrep` that receives `binaryNumbers` as its parameter. This function organizes and sorts a guest list represented by binary numbers.

---

## 🎯 Objectives

Your task is to:

1. **Convert** each binary number in the `binaryNumbers` array to its decimal equivalent
2. **Sort** the converted decimal numbers in ascending order
3. **Return** the sorted array of decimal numbers

---

## 📥 Function Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `binaryNumbers` | `array of strings` | An array of binary numbers represented as strings |

**Example Input:**
```javascript
['1010', '11', '1000', '1111', '10']
```

---

## 📤 Return Value

**Type:** `array of integers`

An array of integers representing the sorted decimal equivalents of the input binary numbers.

**Example Output:**
```javascript
[2, 8, 10, 15]
```

---

## 💡 Function Signature

```javascript
function celebrationPrep(binaryNumbers) {
  // Your implementation here
}
```

---

## 📝 Implementation Steps

**Step 1:** Convert binary strings to decimal
- Use `parseInt(string, 2)` to convert each binary string to decimal

**Step 2:** Sort the decimal numbers
- Use the `.sort()` method with a comparison function

**Step 3:** Return the sorted array
- Return the resulting sorted array of integers

---

## ✅ Example Test Case

**Input:**
```javascript
celebrationPrep(['1010', '11', '1000', '1111', '10'])
```

**Expected Output:**
```javascript
[2, 8, 10, 15]
```

**Explanation:**
- `'10'` → 2
- `'11'` → 3
- `'1000'` → 8
- `'1010'` → 10
- `'1111'` → 15

Then sorted in ascending order: `[2, 8, 10, 15]`

---

## 🚀 Tips for Success

- Remember that binary is base-2, so each digit represents a power of 2
- The `parseInt()` function is your best friend for binary conversion
- Don't forget to use a proper comparison in the sort function
- Consider edge cases like empty arrays or single-element arrays
