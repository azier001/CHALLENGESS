# 🌲 Solitary Walk in the Woods

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that simulates a peaceful walk through the woods, where each step can either move you forward or backward on your path.

---

## 🎯 Problem Description

You need to implement a function named `solitary_walk` that takes an array of numbers representing steps taken during a walk in the woods.

### Function Signature
```javascript
function solitary_walk(steps)
```

### 🚶‍♂️ Walk Mechanics

- **Positive numbers** → Steps forward
- **Negative numbers** → Steps backward
- **Safety Rule**: If the next step would result in a negative total (going behind your starting point), **stop immediately**
- **Goal**: Return the total number of steps taken during the walk

---

## 📝 Requirements

### Input
- `steps`: An array of numbers representing individual steps
  - Contains at least one element
  - Can include positive and negative values

### Output
- A **number** representing the total steps taken during the walk

### Constraints
- ✅ The walk stops if the next step would make the total negative
- ✅ Otherwise, complete the entire walk
- ✅ Always return the cumulative steps taken

---

## 💡 Examples

### Example 1: Complete Walk
```javascript
solitary_walk([2, 3, -1, 4])
// Steps: 0 → 2 → 5 → 4 → 8
// Result: 8
```

### Example 2: Early Termination
```javascript
solitary_walk([3, -2, -4, 1])
// Steps: 0 → 3 → 1 → (would be -3, so stop)
// Result: 1
```

### Example 3: Single Step
```javascript
solitary_walk([5])
// Steps: 0 → 5
// Result: 5
```

---

## 🤔 Implementation Notes

1. **Track Current Position**: Keep a running total of your current position
2. **Look Ahead**: Before taking each step, check if it would result in a negative position
3. **Early Exit**: Stop immediately when a step would make you go negative
4. **Return Total**: Always return the final position (total steps taken)

---

## 🏃‍♂️ Algorithm Approach

1. Initialize current position to `0`
2. For each step in the array:
   - Calculate what the new position would be
   - If new position would be negative, return current position
   - Otherwise, update current position
3. Return final position

---

## ⚠️ Edge Cases to Consider

- Array with only negative numbers
- Array starting with a large negative number
- Mixed positive and negative steps
- Single element arrays

---

**Happy Coding! 🌟**
