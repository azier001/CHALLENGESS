# 📚 Monastery Library Section Sorter

## 🎯 Challenge Overview

**Difficulty Level:** `Easy`

Help the monks organize their ancient library by creating a specialized sorting function! This challenge requires you to implement a function that can sort a specific section of the monastery's book collection while preserving the order of books outside that section.

---

## 📋 Problem Statement

Create a function named `sortMonasteryBooks` that assists monks in sorting a specific section of their library books alphabetically while keeping the rest of the collection unchanged.

### Function Signature

```javascript
function sortMonasteryBooks(books, startIndex, endIndex)
```

---

## 🔧 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `books` | `Array<string>` | An array containing book titles in the library |
| `startIndex` | `number` | The starting index (inclusive) of the section to sort |
| `endIndex` | `number` | The ending index (inclusive) of the section to sort |

---

## 📤 Return Value

- **Type:** `Array<string>`
- **Description:** A new array with the specified section sorted alphabetically, while all other books remain in their original positions

---

## 🎯 Requirements

- ✅ Sort only the books within the specified index range
- ✅ Maintain alphabetical order for the sorted section
- ✅ Keep all other books in their original positions
- ✅ Return a new array (do not modify the original)

---

## 📏 Constraints

| Constraint | Value/Rule |
|------------|------------|
| **Array Length** | Maximum 10 books |
| **Book Titles** | English letters, spaces, and punctuation only |
| **Index Validity** | `startIndex` and `endIndex` will always be valid array indices |
| **Index Relationship** | `startIndex` ≤ `endIndex` |

---

## 💡 Example Usage

```javascript
// Example input
const books = [
    "Divine Comedy", 
    "Zealot's Guide", 
    "Ancient Prayers", 
    "Book of Hours", 
    "Sacred Texts"
];

// Sort books from index 1 to 3
const result = sortMonasteryBooks(books, 1, 3);

// Expected output:
// [
//     "Divine Comedy",     // unchanged (index 0)
//     "Ancient Prayers",   // sorted (was at index 2)
//     "Book of Hours",     // sorted (was at index 3)
//     "Zealot's Guide",    // sorted (was at index 1)
//     "Sacred Texts"       // unchanged (index 4)
// ]
```

---

## 🧠 Approach Hints

1. **Extract** the section to be sorted
2. **Sort** the extracted section alphabetically
3. **Reconstruct** the array with the sorted section in place
4. **Preserve** the original positions of books outside the range

---

## 🏷️ Tags

`#arrays` `#sorting` `#string-manipulation` `#beginner-friendly`

---

*May your code bring order to the monastery's sacred knowledge! 📜✨*
