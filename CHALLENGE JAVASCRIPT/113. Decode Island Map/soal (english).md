# 🏝️ Decode Island Map Challenge

## 📋 Challenge Overview

**Difficulty:** `Easy`

Create a function that decodes a treasure map by counting hidden treasures represented as '1's in an encoded string.

---

## 🎯 Problem Statement

Implement a function named `decodeIslandMap` that:

- **Input:** A string parameter `encodedMap` containing only '0' and '1' characters
- **Output:** An integer representing the total count of '1's (treasures) found in the map
- **Task:** Count all occurrences of the character '1' in the input string

---

## 💡 Example

```javascript
decodeIslandMap("10110")  // Returns: 3
```

**Explanation:** The string "10110" contains three '1's at positions 0, 2, and 3.

---

## ⚡ Function Signature

```javascript
function decodeIslandMap(encodedMap) {
    // Your implementation here
}
```

---

## 📏 Constraints

| Constraint | Value |
|------------|-------|
| **Input Characters** | Only '0' and '1' |
| **String Length** | 1 ≤ length ≤ 100 |
| **Input Type** | String |
| **Output Type** | Integer |

---

## 🧪 Test Cases

### Test Case 1
```javascript
decodeIslandMap("1001")
// Expected Output: 2
// Explanation: Two '1's found at positions 0 and 3
```

### Test Case 2
```javascript
decodeIslandMap("00000")
// Expected Output: 0
// Explanation: No '1's found in the string
```

### Test Case 3
```javascript
decodeIslandMap("1111111")
// Expected Output: 7
// Explanation: All seven characters are '1's
```

---

## 🎨 Visual Representation

```
Input:  "1 0 1 1 0"
         ↓   ↓ ↓
Treasures: 🏆 🏆 🏆
Count: 3
```

---

## 💭 Approach Ideas

- **Method 1:** Iterate through each character and count '1's
- **Method 2:** Use string methods like `split()` or regular expressions
- **Method 3:** Use array methods with `filter()` or `reduce()`

---

## 🔍 Edge Cases to Consider

- Empty string (though constraints specify minimum length of 1)
- String with all '0's
- String with all '1's
- Single character strings

---

*Happy coding! 🚀*
