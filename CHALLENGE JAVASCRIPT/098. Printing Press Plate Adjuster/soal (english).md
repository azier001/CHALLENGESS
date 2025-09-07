# 🖨️ Printing Press Plate Adjuster

## 📋 Challenge Overview
**Difficulty Level:** `Easy`

As a printing press operator, you're tasked with adjusting the plates for a diverse magazine publication. Each plate represents a page of the magazine, and you need to make specific adjustments based on the content of each page.

---

## 🎯 Objective

Create a function named `adjustPrintingPlates` that processes magazine sections and applies specific adjustments based on predefined conditions.

### Function Signature
```javascript
function adjustPrintingPlates(magazineSections)
```

---

## 📝 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `magazineSections` | `Array<Array<string>>` | A 2D array of strings where each inner array represents a page of the magazine |

---

## 🔧 Processing Rules

The function should process each page according to the following conditions **in order of priority**:

### 1. 🚫 **Advertisement Filter**
- **Condition:** If a page contains the word `"advertisement"`
- **Action:** Skip the page entirely (do not include in output)
- **Implementation:** Use `continue` statement

### 2. 🔄 **Long Word Reversal**
- **Condition:** If a page contains any word longer than 10 characters
- **Action:** Reverse the entire page
- **Implementation:** Use array `reverse()` method

### 3. ⚖️ **Middle Element Reversal**
- **Condition:** If a page contains exactly 5 elements
- **Action:** Reverse only the middle 3 elements (indices 1, 2, 3)
- **Implementation:** Extract middle elements, reverse them, then reconstruct

### 4. ✅ **No Changes**
- **Condition:** None of the above conditions are met
- **Action:** Leave the page as is

---

## 📤 Return Value

**Type:** `Array<Array<string>>`  
**Description:** A 2D array of strings representing the adjusted magazine sections

---

## 💡 Implementation Template

```javascript
function adjustPrintingPlates(magazineSections) {
  let adjustedSections = [];
  
  for (let page of magazineSections) {
    // Your code here
    // Remember to use continue for skipping advertisements
    // Use array reverse() method for reversing when needed
    // Don't forget to push the adjusted page to adjustedSections
  }
  
  return adjustedSections;
}
```

---

## 🛠️ Technical Requirements

### Key Concepts to Implement:
- ✅ **Control Flow:** Effective use of `break` and `continue` statements
- ✅ **Array Manipulation:** Working with 2D arrays
- ✅ **String Processing:** Word length validation and content checking
- ✅ **Reversing Algorithms:** Array reversal techniques
- ✅ **Mathematical Logic:** Array indexing and length calculations

### Best Practices:
- Handle edge cases appropriately
- Maintain original array structure
- Use descriptive variable names
- Implement clean, readable code

---

## 🧪 Example Workflow

```
Input Page: ["word1", "word2", "advertisement", "word4"]
↓
Check: Contains "advertisement"? ✅ YES
↓
Action: Skip page (continue to next)
↓
Result: Page not included in output
```

```
Input Page: ["short", "word", "supercalifragilisticexpialidocious"]
↓
Check: Contains word > 10 chars? ✅ YES
↓
Action: Reverse entire page
↓
Result: ["supercalifragilisticexpialidocious", "word", "short"]
```

---

## 📚 Learning Objectives

By completing this challenge, you will practice:

- 🎯 **Conditional Logic:** Implementing complex decision trees
- 🔄 **Array Methods:** Using built-in array manipulation functions
- 📊 **Data Structures:** Working with multi-dimensional arrays
- 🧮 **Algorithm Design:** Creating efficient processing workflows
- 🐛 **Problem Solving:** Breaking down complex requirements into manageable steps

---

*Good luck with your implementation! Remember to test your function with various input scenarios to ensure it handles all conditions correctly.* 🚀
