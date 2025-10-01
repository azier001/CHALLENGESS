# 🌿 Botanist's Rare Plant Search

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

---

## 🎯 Problem Statement

A frustrated botanist is searching for a specific rare plant in a field full of various plants. Due to their confusion, some plant names in their notes might be **accidentally reversed**. 

Your mission is to help the botanist find the rare plant they're looking for by creating a search function that accounts for both normal and reversed spellings.

---

## 💻 Function Requirements

### Function Signature

```javascript
function findRarePlant(plantNames, rarePlant)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `plantNames` | `array` | An array of strings representing different plant names found in the field. Some names might be reversed. |
| `rarePlant` | `string` | The name of the rare plant the botanist is searching for. |

### Return Value

- **Type:** `integer`
- **Returns:** 
  - The **index** of the matching plant in the `plantNames` array (if found in normal or reversed form)
  - `-1` if the plant is not found

---

## 🔧 Implementation Guide

### Helper Function

You can use this helper function to reverse strings:

```javascript
function reverseString(str) {
    return str.split('').reverse().join('');
}
```

### Task Checklist

- [ ] Search through the `plantNames` array
- [ ] Check if `rarePlant` matches any plant name (normal spelling)
- [ ] Check if `rarePlant` matches any plant name (reversed spelling)
- [ ] Return the index of the first match found
- [ ] Return `-1` if no match is found

---

## 📝 Example Scenarios

### Scenario 1: Normal Match
```javascript
plantNames = ["rose", "tulip", "orchid"]
rarePlant = "tulip"
// Expected output: 1
```

### Scenario 2: Reversed Match
```javascript
plantNames = ["rose", "pilut", "orchid"]
rarePlant = "tulip"
// Expected output: 1 (because "pilut" reversed is "tulip")
```

### Scenario 3: Not Found
```javascript
plantNames = ["rose", "orchid", "daisy"]
rarePlant = "tulip"
// Expected output: -1
```

---

## 💡 Tips

- Consider both the normal and reversed forms of plant names in the array
- The rare plant name (`rarePlant`) should be compared against both forms
- Remember to return the **first** matching index
- String manipulation methods like `split()`, `reverse()`, and `join()` are your friends!

---

## 🚀 Ready to Start?

Now it's your turn to implement the `findRarePlant` function and help the botanist locate their precious rare plant!
