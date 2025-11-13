# 📚 Bookstore Anagram Display Groups

## Challenge Overview

**Difficulty Level:** `Medium` 🟡

---

## 🎯 Objective

Write a function `groupAnagramTitles` that organizes book titles into groups based on anagram relationships. This helps you create creative display arrangements in your bookstore by grouping books that share the same letters!

---

## 📋 Function Specification

### Function Signature

```javascript
function groupAnagramTitles(bookTitles)
```

### Parameters

- **`bookTitles`** *(array)*  
  An array of book title strings to be grouped by anagram relationships.

### Returns

- **2D Array** of anagram groups  
  - Each sub-array contains book titles that are anagrams of each other
  - Original title formatting is preserved
  - Format: `[["Title One", "Title Two"], ["Single Title"], ["Another", "Group"]]`

---

## 🔍 Logic & Requirements

The function should follow these steps:

1. **Create Signature**  
   For each title, generate a unique signature by:
   - Converting to the same case (ignore case differences)
   - Removing spaces
   - Sorting all letters alphabetically

2. **Group by Signature**  
   - Titles with identical signatures are anagrams
   - Place them together in the same sub-array

3. **Preserve Original Format**  
   - Keep the original capitalization and spacing of titles
   - Don't modify the input strings

4. **Handle Singles**  
   - Titles without anagrams should still appear in their own sub-array
   - Every title must be included in the output

---

## 💡 Example Scenarios

### Example 1: Basic Anagram Grouping

**Input:**
```javascript
["Listen", "Silent", "Hello", "World"]
```

**Output:**
```javascript
[
  ["Listen", "Silent"],
  ["Hello"],
  ["World"]
]
```

---

### Example 2: Multiple Groups

**Input:**
```javascript
["The Eyes", "They See", "Act", "Cat", "Book"]
```

**Output:**
```javascript
[
  ["The Eyes", "They See"],
  ["Act", "Cat"],
  ["Book"]
]
```

---

## 🎨 Use Case

Perfect for creating eye-catching bookstore displays where books with anagram titles are grouped together, adding a playful and intellectual element to your inventory organization!

---

## ⚡ Key Points to Remember

- ✅ Case-insensitive comparison
- ✅ Ignore spaces when comparing
- ✅ Maintain original title format in output
- ✅ Every title appears exactly once
- ✅ Single titles get their own sub-array

---

**Happy Coding!** 🚀
