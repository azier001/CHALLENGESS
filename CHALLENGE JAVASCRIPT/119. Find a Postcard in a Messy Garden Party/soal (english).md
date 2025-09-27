# 🌻 Find a Postcard in a Messy Garden Party

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function named `findReversePostcard` that helps locate a specific postcard in a pile that has been accidentally stacked in reverse order after a chaotic garden party.

---

## 🎯 Challenge Description

Imagine you're at a messy garden party where guests have been exchanging peculiar postcards. After the party ends, the postcards are accidentally stacked in reverse order, creating quite the mess! Your mission is to help find a specific postcard in this jumbled pile.

---

## 🔧 Function Specification

### Function Name
```javascript
findReversePostcard(postcards, message)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `postcards` | `Array<String>` | An array of strings, where each string represents a message on a postcard |
| `message` | `String` | The specific message to find among the postcards |

### Return Value
- **Type:** `Number`
- **Description:** The index of the found postcard in the reversed array, or `-1` if the message is not found

---

## 📝 Algorithm Steps

The function should perform the following operations in sequence:

1. **🔄 Reverse the Array**
   - Reverse the order of the postcards array to simulate the mess from the party

2. **🔍 Search for Message**
   - Search for the specified message in the reversed array of postcards

3. **📍 Return Index**
   - If the message is found → return the index of the postcard in the reversed array
   - If the message is not found → return `-1`

---

## 💡 Example Usage

```javascript
// Example postcards from the garden party
const postcards = [
    "Hello from the rose garden!",
    "The sunflowers are blooming beautifully",
    "Thanks for the lovely tea party",
    "See you next spring!"
];

const targetMessage = "Thanks for the lovely tea party";

// Function call
const result = findReversePostcard(postcards, targetMessage);

// Expected behavior:
// 1. Reversed array: ["See you next spring!", "Thanks for the lovely tea party", "The sunflowers are blooming beautifully", "Hello from the rose garden!"]
// 2. Search for "Thanks for the lovely tea party"
// 3. Found at index 1 in the reversed array
// 4. Return: 1
```

---

## ⚡ Key Points to Remember

- 🔄 Always reverse the array **first** before searching
- 📍 Return the index from the **reversed array**, not the original
- ❌ Return `-1` when the message is not found
- 🎯 Exact string matching is required

---

## 🏷️ Tags

`Array Manipulation` • `String Search` • `Index Finding` • `Algorithm` • `Easy Challenge`
