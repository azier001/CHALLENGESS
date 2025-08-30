# 🐦 Bird Code Generator Challenge

## 📋 Challenge Overview

**Difficulty:** `Easy`

Create a function named `birdCode` that analyzes bird names and generates special codes based on mathematical and linguistic properties.

---

## 🎯 Function Specification

### Function Signature
```javascript
function birdCode(birdName)
```

**Parameter:**
- `birdName` (string): The name of the bird to analyze

**Return:**
- String containing the generated code

---

## 🔍 Code Generation Rules

The function evaluates three distinct conditions and builds a code accordingly:

### Rule 1: Prime Vowel Count
- **Condition:** Bird name contains a **prime number** of vowels
- **Action:** Add `"1"` to the code
- **Vowels:** `a`, `e`, `i`, `o`, `u` (case-insensitive)

### Rule 2: Perfect Square Length
- **Condition:** Bird name length is a **perfect square**
- **Action:** Add `"2"` to the code
- **Perfect squares:** 1, 4, 9, 16, 25, 36, 49, 64, 81, 100...

### Rule 3: Palindrome Detection
- **Condition:** Bird name is a **palindrome**
- **Action:** Add `"3"` to the code
- **Palindrome:** Reads the same forwards and backwards

### Default Case
- **Condition:** None of the above rules apply
- **Action:** Return `"0"`

---

## 📚 Key Definitions

| Term | Definition | Examples |
|------|------------|----------|
| **Vowels** | Letters: a, e, i, o, u (uppercase/lowercase) | `"Eagle"` has 3 vowels: e, a, e |
| **Prime Number** | Natural number > 1 with exactly two divisors | 2, 3, 5, 7, 11, 13, 17, 19, 23... |
| **Perfect Square** | Integer that equals n² for some integer n | 1=1², 4=2², 9=3², 16=4², 25=5² |
| **Palindrome** | Word reading same forwards and backwards | "racecar", "madam", "level" |

---

## 💡 Example Scenarios

### Multiple Conditions
If a bird name satisfies multiple rules, concatenate all applicable codes:
- ✅ Prime vowels + Perfect square length → `"12"`
- ✅ Prime vowels + Palindrome → `"13"`
- ✅ Perfect square + Palindrome → `"23"`
- ✅ All three conditions → `"123"`

### Sample Test Cases
```
birdCode("Eagle")     // Analyze vowel count, length, palindrome
birdCode("Owl")       // Check all three conditions
birdCode("Raven")     // Evaluate based on rules
birdCode("Dove")      // Apply conditions sequentially
```

---

## 🚀 Implementation Tips

1. **Vowel Counting:** Use case-insensitive matching
2. **Prime Checking:** Implement efficient prime detection
3. **Perfect Square:** Use square root validation
4. **Palindrome:** Compare string with its reverse
5. **Code Building:** Concatenate conditions in order (1→2→3)

---

## ⚡ Quick Reference

```
Condition Met → Code Addition
─────────────────────────────
Prime vowels  →     "1"
Perfect square→     "2"  
Palindrome    →     "3"
None          →     "0"
```

---

*Good luck with your implementation! 🎯*
