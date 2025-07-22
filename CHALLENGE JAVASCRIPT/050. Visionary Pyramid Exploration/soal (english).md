# 🔺 Visionary Pyramid Challenge

## 📋 Overview

**Difficulty:** `Easy`

This challenge involves creating a function that constructs a unique pyramid structure with specific number patterns and formatting requirements.

---

## 🎯 Objective

Create a function named `visionaryPyramid` that builds a pyramid with the following characteristics:

- **Odd numbers only** in the pyramid structure
- **Skip pattern** when encountering numbers divisible by 5
- **Centered alignment** for visual appeal
- **Incremental levels** based on input parameter

---

## 📝 Function Specification

### Function Signature
```javascript
function visionaryPyramid(maxLevels)
```

### Parameters

| Parameter | Type | Description | Constraints |
|-----------|------|-------------|-------------|
| `maxLevels` | `integer` | The maximum number of levels in the pyramid | `1 ≤ maxLevels ≤ 10` |

### Return Value

- **Type:** `Array of Strings`
- **Description:** Each element represents a level of the pyramid with properly spaced and centered numbers

---

## 🔧 Implementation Requirements

### Core Logic

1. **Nested Loop Structure**
   - **Outer loop:** Iterates from 1 to `maxLevels` (represents each pyramid level)
   - **Inner loop:** Generates odd numbers for each level

2. **Number Generation Rules**
   - Start with odd numbers only
   - Continue from where the previous level ended
   - When encountering a number divisible by 5, use `continue` to skip the next number

3. **Formatting Requirements**
   - Each level must be properly aligned and centered
   - Numbers within a level separated by a single space
   - Use string manipulation techniques for alignment

### Key Programming Concepts

- ✅ **Nested loops**
- ✅ **Continue statement**
- ✅ **String manipulation**
- ✅ **Array handling**
- ✅ **Conditional logic**

---

## 💡 Expected Behavior

The function should:

1. Generate a pyramid with the specified number of levels
2. Fill each level with consecutive odd numbers
3. Skip numbers according to the divisibility-by-5 rule
4. Format output with proper centering and spacing
5. Return an array where each element represents one pyramid level

---

## 🎨 Visual Example

```
    1
   3 7
  9 11 13
 15 17 19 21
```
*Example output format (actual numbers may vary based on skip logic)*

---

## ⚠️ Important Notes

- The pyramid structure should maintain visual symmetry
- Handle the `continue` statement correctly when numbers are divisible by 5
- Ensure proper string formatting for alignment
- Validate that `maxLevels` is within the specified range

---

## 🏷️ Tags

`#algorithms` `#loops` `#string-manipulation` `#pyramid` `#javascript` `#easy-challenge`
