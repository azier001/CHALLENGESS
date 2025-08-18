# 🌾 Sort Crops Array with Lucky Number 13

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function that sorts an array of crop numbers, but with a twist involving the lucky number 13!

---

## 🎯 Objective

Create a function named `sortCrops` that:
- Receives an array of numbers called `cropsArray`
- Sorts the array in **ascending order**
- **Special Rule:** If the number `13` appears in the array, stop sorting at that position and return the partially sorted array

---

## 📝 Function Specification

```javascript
function sortCrops(cropsArray) {
    // Your implementation here
}
```

### Parameters
- `cropsArray` (Array): An array of numbers representing crops

### Returns
- Array: The sorted (or partially sorted) `cropsArray`

---

## 💡 Examples

### Example 1: Normal Sorting
```javascript
Input:  [4, 2, 7, 1]
Output: [1, 2, 4, 7]
```
*No 13 present - complete ascending sort*

### Example 2: Early 13 Encounter
```javascript
Input:  [9, 13, 5, 2, 8]
Output: [9, 13, 5, 2, 8]
```
*13 at index 1 - no sorting performed*

### Example 3: Mid-Array 13 Encounter
```javascript
Input:  [6, 3, 13, 10, 2, 5]
Output: [3, 6, 13, 10, 2, 5]
```
*13 at index 2 - elements before index 2 are sorted*

---

## 🔍 Key Rules

1. **Ascending Order**: Sort numbers from smallest to largest
2. **Lucky Number 13**: When encountered, stop sorting immediately
3. **Partial Sorting**: Only sort elements **before** the position of 13
4. **Return Original**: If 13 is at the beginning, return the array unchanged

---

## 🧠 Algorithm Hints

- Find the index of number 13 first
- If 13 exists, only sort the subarray before that index
- If 13 doesn't exist, sort the entire array
- Combine the sorted portion with the remaining unsorted portion

---

## ✅ Success Criteria

Your function should:
- ✓ Handle arrays without 13 (complete sort)
- ✓ Handle arrays with 13 at any position (partial sort)
- ✓ Maintain original order after 13's position
- ✓ Return the modified `cropsArray`

---

*Happy coding! 🚀*
