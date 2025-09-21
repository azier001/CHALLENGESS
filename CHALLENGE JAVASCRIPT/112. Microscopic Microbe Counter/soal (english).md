# 🔬 Microscopic Microbe Counter

## Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function that counts different types of microorganisms observed under a microscope and returns their frequency distribution.

---

## 📋 Problem Description

Your task is to develop a function named `microbeCounter` that analyzes microscopic samples and provides statistical data about the observed microbes.

### Function Specification

```javascript
function microbeCounter(sample) {
    // Your implementation here
}
```

---

## 🔧 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `sample` | `Array<string>` | An array of strings representing the microbes observed under the microscope |

---

## 📤 Return Value

The function should return an **object** with the following characteristics:
- **Keys**: Unique microbe names (strings)
- **Values**: Count of each microbe in the sample (integers)

---

## 💡 Example

### Input
```javascript
["amoeba", "paramecium", "amoeba", "euglena"]
```

### Expected Output
```javascript
{
  "amoeba": 2,
  "paramecium": 1,
  "euglena": 1
}
```

### Visual Representation
```
🦠 amoeba      ██ (2 occurrences)
🦠 paramecium  █  (1 occurrence)
🦠 euglena     █  (1 occurrence)
```

---

## 🎯 Key Requirements

- ✅ Function must be named `microbeCounter`
- ✅ Accept one parameter: `sample` (array)
- ✅ Return an object with microbe counts
- ✅ Handle duplicate microbe names correctly
- ✅ Preserve original microbe name casing

---

## 🧪 Test Cases

Consider testing your function with various scenarios:

1. **Empty sample**: `[]`
2. **Single microbe**: `["bacteria"]`
3. **All same microbes**: `["virus", "virus", "virus"]`
4. **Mixed case sensitivity**: `["Amoeba", "amoeba"]`
5. **Large dataset**: Array with 100+ microbe entries

---

## 🎨 Implementation Tips

> 💡 **Hint**: Consider using object property access patterns and iteration methods to build your solution efficiently.

Good luck with your microscopic analysis! 🔬✨
