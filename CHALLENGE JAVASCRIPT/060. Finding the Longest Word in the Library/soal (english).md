# 📚 Finding the Longest Word in the Library

## 🎯 Challenge Overview

**Difficulty Level:** `Easy`

Picture yourself in a quiet library on a peaceful afternoon, surrounded by old books and forgotten words. Your mission is to discover the longest word among a collection of words from these ancient tomes.

---

## 📋 Task Description

Create a function named `findLongestWord` that takes an array of words and returns the longest word found.

### 🔧 Function Signature

```javascript
function findLongestWord(words) {
    // Your implementation here
}
```

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `words` | `Array<string>` | An array of strings, where each string represents a word from the library books |

---

## 📤 Return Value

- **Type:** `string`
- **Description:** The longest word found in the input array
- **Special Case:** If multiple words have the same maximum length, return the **first one encountered**

---

## 🛠️ Implementation Guidelines

Follow these steps to solve the challenge:

1. **Initialize** a variable to store the longest word, starting with an empty string
2. **Loop** through each word in the input array using basic loops (`for` or `while`)
3. **Compare** each word's length with the current longest word's length
4. **Update** the longest word variable if the current word is longer
5. **Return** the longest word after checking all words

---

## 📏 Code Requirements

- ✅ Use basic loops (`for` or `while` loops)
- ✅ Code length: **10-19 lines**
- ✅ Handle edge cases appropriately
- ✅ Follow the algorithm steps outlined above

---

## 💡 Example Scenario

```javascript
// Example usage
const libraryWords = ["ancient", "tome", "manuscript", "scroll", "book"];
const result = findLongestWord(libraryWords);
// Expected: "manuscript" (10 characters)
```

---

## 🎨 Visual Algorithm Flow

```
Start
  ↓
Initialize longestWord = ""
  ↓
For each word in words array
  ↓
Is current word longer than longestWord?
  ↓ Yes        ↓ No
Update         Continue
longestWord    to next word
  ↓              ↓
Continue ←-------
  ↓
All words checked?
  ↓ Yes
Return longestWord
  ↓
End
```

---

## 🎯 Key Points to Remember

> - Focus on **length comparison**, not alphabetical order
> - Return the **first** longest word if there are ties
> - Use **basic loop structures** as specified
> - Keep your solution **clean and readable**

---

*Happy coding! May you find the longest words in the digital library! 📖✨*
