# 🌊 Reservoir Word Play Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that manipulates strings based on palindrome detection. This challenge combines string manipulation, palindrome checking, and conditional logic.

---

## 🎯 Objective

Implement a function named `reservoirWordPlay` that processes input strings differently based on whether they are palindromes or not.

---

## 🔧 Function Specification

### Function Signature
```javascript
function reservoirWordPlay(word)
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `word` | `string` | The input string to be manipulated |

### Return Value
- **Type:** `string`
- **Description:** The manipulated string based on palindrome condition

---

## ⚡ Algorithm Logic

The function follows a two-step decision process:

### 🔄 Case 1: Palindrome Detected
> When the input string reads the same forwards and backwards

**Action:** Remove all vowels
- **Target vowels:** `a`, `e`, `i`, `o`, `u` (case-insensitive)
- **Process:** Filter out vowel characters from the string
- **Return:** Modified string without vowels

### 🔄 Case 2: Not a Palindrome
> When the input string reads differently forwards and backwards

**Action:** Reverse the string
- **Process:** Reverse the character order
- **Return:** Reversed string

---

## 📝 Examples

### Example 1: Palindrome Input
```
Input: "racecar"
✓ Is palindrome: true
→ Remove vowels: "rccr"
Output: "rccr"
```

### Example 2: Non-Palindrome Input
```
Input: "hello"
✗ Is palindrome: false
→ Reverse string: "olleh"
Output: "olleh"
```

### Example 3: Palindrome with Mixed Case
```
Input: "Level"
✓ Is palindrome: true (case-insensitive check)
→ Remove vowels: "Lvl"
Output: "Lvl"
```

---

## 🧪 Test Cases

| Input | Is Palindrome? | Action | Expected Output |
|-------|----------------|---------|-----------------|
| `"racecar"` | ✅ Yes | Remove vowels | `"rccr"` |
| `"hello"` | ❌ No | Reverse | `"olleh"` |
| `"madam"` | ✅ Yes | Remove vowels | `"mdm"` |
| `"world"` | ❌ No | Reverse | `"dlrow"` |
| `"noon"` | ✅ Yes | Remove vowels | `"nn"` |

---

## 💡 Implementation Tips

1. **Palindrome Check:** Compare the string with its reversed version (case-insensitive)
2. **Vowel Removal:** Use regular expressions or string methods to filter vowels
3. **String Reversal:** Utilize built-in string methods or array manipulation
4. **Edge Cases:** Consider empty strings, single characters, and special characters

---

## 🏷️ Tags
`String Manipulation` `Palindrome` `Conditional Logic` `Algorithm` `Easy Challenge`
