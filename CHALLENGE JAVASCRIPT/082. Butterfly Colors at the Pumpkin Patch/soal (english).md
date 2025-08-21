# 🦋 Butterfly Colors at the Pumpkin Patch

## Challenge Overview

**Difficulty Level:** `Easy`

Create a function that counts the occurrence of different butterfly colors observed at a pumpkin patch. This is a perfect beginner-friendly challenge that focuses on array iteration and object manipulation.

---

## 📋 Problem Description

You need to implement a function named `countButterflyColors` that processes an array of butterfly colors and returns a summary object showing how many times each color appears.

### What the Function Should Do:

1. **Receive** an array of color strings as input
2. **Iterate** through each color in the array
3. **Count** how many times each unique color appears
4. **Return** an object with colors as keys and counts as values

---

## 🔧 Function Specification

### Function Name
```javascript
countButterflyColors
```

### Parameters

| Parameter | Type | Description | Constraints |
|-----------|------|-------------|-------------|
| `colors` | `Array<String>` | Array of butterfly color strings | Length: 2-100 elements |

### Return Value

- **Type:** `Object`
- **Structure:** `{ colorName: count, ... }`
- **Keys:** Unique color names (strings)
- **Values:** Occurrence count (integers)

---

## 📊 Example Usage

```javascript
// Example Input
const butterflyColors = ["red", "blue", "red", "yellow", "blue", "red"];

// Expected Output
{
  "red": 3,
  "blue": 2,
  "yellow": 1
}
```

---

## ✅ Requirements Checklist

- [ ] Function name must be exactly `countButterflyColors`
- [ ] Must accept one parameter named `colors`
- [ ] Handle arrays with 2-100 elements
- [ ] Return an object with color-count pairs
- [ ] Count each unique color correctly
- [ ] Handle duplicate colors appropriately

---

## 🎯 Key Concepts

This challenge helps you practice:

- **Array Iteration** - Looping through array elements
- **Object Manipulation** - Creating and updating object properties
- **Conditional Logic** - Checking if properties exist
- **Counting Algorithms** - Tracking occurrence frequencies

---

## 💡 Hints

> **Tip 1:** Consider using a loop to iterate through the colors array
> 
> **Tip 2:** Check if a color already exists in your result object before incrementing
> 
> **Tip 3:** Initialize new colors with a count of 1, increment existing ones

---

## 🏷️ Tags

`#JavaScript` `#Arrays` `#Objects` `#Counting` `#Beginner` `#DataStructures`
