# 🏖️ Reversing Beach Day Memories

## 📋 Challenge Overview

**Difficulty:** `Easy`

Create a function that reverses both array elements and string characters, simulating the process of looking back at beach day memories in reverse order.

---

## 🎯 Objective

Implement a function named `reverseBeachDay` that takes an array of items and a phrase, then returns both in reversed order.

---

## 📝 Function Specification

### Function Name
```javascript
reverseBeachDay(items, phrase)
```

### Parameters

| Parameter | Type | Description | Constraints |
|-----------|------|-------------|-------------|
| `items` | `Array<string>` | An array of strings representing beach day items | 1-10 items, each 1-100 characters |
| `phrase` | `string` | A string representing a beach day phrase | 1-100 characters |

### Return Value

**Type:** `Array`

**Structure:** `[reversedItems, reversedPhrase]`
- **First element:** The `items` array with its elements in reversed order
- **Second element:** The `phrase` string with its characters in reversed order

---

## 💡 Implementation Guidelines

### For Array Reversal
- Use the built-in `reverse()` method to reverse the order of elements in the `items` array

### For String Reversal
1. Convert the string into an array of characters
2. Reverse the character array
3. Join the characters back into a string

---

## 📚 Example Usage

```javascript
// Example 1
const items = ["sunscreen", "towel", "beach ball"];
const phrase = "sunny day";
const result = reverseBeachDay(items, phrase);
// Expected output: [["beach ball", "towel", "sunscreen"], "yad ynnus"]

// Example 2
const items = ["sandcastle", "seashells"];
const phrase = "ocean waves";
const result = reverseBeachDay(items, phrase);
// Expected output: [["seashells", "sandcastle"], "sevaw naeco"]
```

---

## ✅ Success Criteria

- [ ] Function correctly reverses the order of array elements
- [ ] Function correctly reverses the order of string characters
- [ ] Function returns an array with exactly two elements
- [ ] Function handles edge cases (single item array, single character string)
- [ ] Function respects the parameter constraints

---

## 🔧 Technical Notes

> **Note:** The `reverse()` method modifies the original array. Consider whether you need to create a copy of the original array before reversing it, depending on your implementation requirements.

> **Tip:** For string reversal, you can use the following method chain:
> ```javascript
> string.split('').reverse().join('')
> ```

---

*Happy coding! 🏖️✨*
