# 🗺️ Strange Adventure: Decipher the Hidden Message

## 📋 Challenge Overview

**Difficulty:** `Medium`

Create a function that deciphers hidden messages by analyzing string patterns and character arrangements. This challenge combines string manipulation, pattern matching, and algorithmic thinking.

---

## 🎯 Function Signature

```javascript
function strangeAdventure(clues, cipher)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `clues` | `Array<string>` | An array of strings containing potential hidden messages |
| `cipher` | `string` | A reference string used to identify matching patterns |

### Return Value

- **Type:** `string`
- **Returns:** The deciphered hidden message or `"No hidden message found!"` if no matches exist

---

## 🔍 Algorithm Steps

### Step 1: Initialize Storage
```javascript
let decipheredClues = [];
```
Create an empty array to store valid substring matches.

### Step 2: Extract and Compare Substrings

For each string in the `clues` array:

1. **Extract substrings** that match the length of the `cipher` string
2. **Compare each substring** with the `cipher`:
   - Check if they have the **same length**
   - Verify they contain the **same characters** (order doesn't matter)
3. **Add matching substrings** to `decipheredClues`

> 💡 **Tip:** Use character frequency comparison or sorting to check if two strings are anagrams

### Step 3: Handle Empty Results

```javascript
if (decipheredClues.length === 0) {
    return "No hidden message found!";
}
```

If no matching substrings are found, return the failure message.

### Step 4: Process the Deciphered Clues

#### 4a. Sort by Character Code Sum

Sort `decipheredClues` based on the sum of character codes (ASCII values) of each clue.

```javascript
// Example character code sum calculation
// "abc" → 97 + 98 + 99 = 294
```

#### 4b. Concatenate Sorted Clues

```javascript
let hiddenMessage = decipheredClues.join('');
```

Merge all sorted clues into a single string.

#### 4c. Transform the Message

Apply character transformations:

| Original Character | Transformation |
|-------------------|----------------|
| Uppercase letter | Replace with **space** ` ` |
| Lowercase letter | Convert to **uppercase** |

#### 4d. Return the Result

Return the transformed `hiddenMessage`.

---

## 📝 Example Walkthrough

### Input
```javascript
clues = ["The quick brown", "fox jumps over", "the lazy dog"];
cipher = "abc";
```

### Process
1. Extract 3-character substrings: `"The"`, `"qui"`, `"ick"`, etc.
2. Find matches (anagrams of `"abc"`): `"bac"`, `"cab"`, etc.
3. Sort by character code sum
4. Concatenate and transform

### Output
```javascript
"HIDDEN MESSAGE"
```

---

## 🎓 Key Concepts

- **String Manipulation**: Substring extraction and character operations
- **Anagram Detection**: Comparing character frequencies
- **Sorting Algorithms**: Custom sorting by calculated values
- **ASCII Operations**: Working with character codes
- **String Transformation**: Character case and replacement

---

## ⚡ Performance Considerations

- **Time Complexity**: O(n × m × k) where:
  - `n` = number of clues
  - `m` = average length of each clue
  - `k` = length of cipher
- **Space Complexity**: O(d) where `d` = number of deciphered clues

---

## 🚀 Challenge Tips

1. Use helper functions to keep code organized
2. Consider edge cases (empty arrays, single characters)
3. Optimize anagram checking with character frequency maps
4. Test with various cipher lengths and clue combinations

---

**Good luck, adventurer! May you decipher the hidden message! 🔐✨**
