# 🚢 Seaway Sightseeing Journey

> **Difficulty Level:** `Easy`

---

## 📋 Challenge Overview

Create a function named `seawaySightseeing` that counts the number of each sight spotted during a boat ride and returns an object mapping each sight to its count.

---

## 🎯 Objective

Your task is to implement a function that processes an array of sightings and produces a frequency count of each unique sight encountered during the journey.

---

## 🛠️ Function Specification

### Function Name
```javascript
seawaySightseeing(sights)
```

### Parameter

| Parameter | Type | Description |
|-----------|------|-------------|
| `sights` | `Array<string>` | An array where each element represents a sight spotted during the boat ride. Sights can be repeated. |

### Return Value

**Type:** `Object`

An object where:
- **Keys** = Unique sights spotted (strings)
- **Values** = Count of each sight (numbers)

---

## 📝 Implementation Steps

Follow these steps to solve the challenge:

1. **Initialize** an empty object to store the count of each sight

2. **Loop through** the `sights` array

3. **For each sight:**
   - If the sight doesn't exist in the object → add it with a count of `1`
   - If the sight exists → increment its count by `1`

4. **Return** the object containing the sight counts

---

## 💡 Example

### Input
```javascript
const sights = ['dolphin', 'whale', 'seagull', 'dolphin', 'whale', 'dolphin'];
```

### Expected Output
```javascript
{
  dolphin: 3,
  whale: 2,
  seagull: 1
}
```

---

## ✅ Key Points to Remember

- Handle **duplicate sights** correctly by incrementing their count
- Return an **object**, not an array
- Sight names are **case-sensitive**
- The order of keys in the returned object doesn't matter

---

## 🚀 Getting Started

Begin by creating your function structure:

```javascript
function seawaySightseeing(sights) {
  // Your code here
}
```

Good luck with your seaway adventure! 🌊
