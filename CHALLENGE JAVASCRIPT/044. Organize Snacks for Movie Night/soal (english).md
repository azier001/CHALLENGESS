# 🍿 Movie Night Snack Organizer Challenge

## 🎯 Challenge Overview

**Difficulty Level:** `Easy`

Create a cozy movie night experience by organizing the perfect snack selection! Your task is to build a function that sorts a portion of snacks alphabetically for the ultimate movie night in a furnished living room.

---

## 📋 Function Requirements

### Function Signature
```javascript
function arrangeMovieNight(snacks, start, end)
```

### 🎬 What It Does
The `arrangeMovieNight` function takes a collection of movie snacks and returns a perfectly organized, alphabetically sorted selection based on specified indices.

---

## 🔧 Implementation Steps

Follow these steps to complete the challenge:

1. **Extract Selection** 
   - Use the `start` and `end` indices to extract a portion from the `snacks` array
   
2. **Sort Alphabetically**
   - Sort the extracted portion in alphabetical order
   
3. **Return Result**
   - Return the sorted selection as an array

---

## 📊 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `snacks` | `array` | An array of strings representing different snacks and drinks for movie night |
| `start` | `number` | Starting index for selection (**inclusive**) |
| `end` | `number` | Ending index for selection (**exclusive**) |

---

## 🎯 Return Value

**Type:** `Array<string>`

**Description:** A sorted selection of snacks based on the given start and end indices.

---

## ⚠️ Important Notes

> **Boundary Handling:** Make sure to handle cases where `start` and `end` might be out of bounds of the `snacks` array. If they are, adjust them to fit within the array's bounds.

### Edge Cases to Consider:
- `start` index is negative
- `end` index exceeds array length
- `start` is greater than `end`
- Empty array input

---

## 💡 Example Usage

```javascript
// Example snacks array
const movieSnacks = [
  "Popcorn", "Soda", "Candy", "Chips", "Nachos", 
  "Ice Cream", "Cookies", "Pretzels"
];

// Extract and sort snacks from index 2 to 5
const result = arrangeMovieNight(movieSnacks, 2, 5);
// Expected output: ["Candy", "Chips", "Nachos"] (sorted alphabetically)
```

---

## 🏆 Success Criteria

- ✅ Function extracts correct portion of array
- ✅ Extracted portion is sorted alphabetically
- ✅ Handles out-of-bounds indices gracefully
- ✅ Returns proper array format

---

*Ready to create the perfect movie night snack lineup? Let's get coding! 🎬*
