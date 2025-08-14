# 🌲 Forest Stroll Challenge

## 📋 Overview

**Difficulty Level:** `Easy`

Create a function that simulates an enchanting walk through a mystical forest, where each step brings new encounters with woodland creatures!

---

## 🎯 Challenge Description

Implement a function named **`forestStroll`** that takes a parameter `n` and simulates a peaceful stroll through a forest. During this journey:

- Each **step** is represented by an asterisk (`*`)
- **Animal encounters** are represented by specific letters
- The path is determined by mathematical patterns based on step numbers

---

## 🐾 Animal Encounter Rules

Your forest adventure follows these magical encounter patterns:

| Step Condition | Animal Encountered | Symbol | Description |
|---|---|---|---|
| **Divisible by 3** | Deer | `d` | 🦌 Graceful forest dweller |
| **Divisible by 5** | Rabbit | `r` | 🐰 Quick woodland hopper |
| **Divisible by both 3 AND 5** | Bear | `b` | 🐻 Mighty forest guardian |
| **All other steps** | Regular step | `*` | ⭐ Peaceful walking |

> **Note:** When a step is divisible by both 3 and 5 (i.e., divisible by 15), you encounter a bear, which takes precedence over deer and rabbit encounters.

---

## 🔧 Function Specification

### Function Signature
```javascript
function forestStroll(n)
```

### Parameters
- **`n`** *(integer)*: The total number of steps taken during the forest stroll
  - Must be a positive integer
  - Represents the length of your journey

### Return Value
- **Type:** `string`
- **Content:** A string representing the complete path of your forest adventure
- **Format:** Each character represents either a step (`*`) or an animal encounter (`d`, `r`, or `b`)

---

## 📝 Examples

### Example 1: Short Stroll
```javascript
forestStroll(5)
// Expected output: "*d**r"
// Step 1: * (not divisible by 3 or 5)
// Step 2: * (not divisible by 3 or 5) 
// Step 3: d (divisible by 3 - deer encounter)
// Step 4: * (not divisible by 3 or 5)
// Step 5: r (divisible by 5 - rabbit encounter)
```

### Example 2: Extended Journey
```javascript
forestStroll(15)
// Expected output: "*d*r*d**rd**r*b"
// Notable encounters:
// Step 3, 6, 9, 12: deer (d)
// Step 5, 10: rabbit (r) 
// Step 15: bear (b) - divisible by both 3 and 5
```

---

## 💡 Implementation Hints

1. **Loop through steps:** Iterate from 1 to `n` (inclusive)
2. **Check divisibility:** Use the modulo operator (`%`) to test divisibility
3. **Priority order:** Remember that bear encounters (divisible by 15) override individual deer/rabbit rules
4. **String building:** Concatenate characters to build the final path string

---

## 🎨 Visual Representation

```
Step:   1  2  3  4  5  6  7  8  9  10 11 12 13 14 15
Path:   *  *  d  *  r  d  *  *  d  r  *  d  *  *  b
```

Happy coding, and enjoy your forest adventure! 🌟
