# 🚣 Counting River Obstacles

## 📊 Challenge Level
**Easy**

---

## 🎯 Overview

Imagine a rickety old boat slowly drifting along a peaceful river. Your task is to count the number of obstacles the boat encounters during its journey.

The river is represented by an array where each element is either a **clear path** (`0`) or an **obstacle** (`1`). The boat starts at the beginning of the array and moves forward, encountering each element one by one.

---

## 📝 Problem Statement

Create a function named `countRiverObstacles` that receives `river` as its parameter and counts the total number of obstacles in the river.

---

## 🔧 Function Signature

```javascript
function countRiverObstacles(river)
```

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `river` | Array | An array of numbers representing the river. Each element is either `0` (clear path) or `1` (obstacle) |

---

## 📤 Return Value

- **Type**: `Integer`
- **Description**: The total number of obstacles encountered in the river

---

## 💡 Approach

Here's a recommended approach to solve this problem:

1. **Initialize** a counter variable to keep track of obstacles
2. **Iterate** through each element in the river array
3. **Check** if an element is `1` (an obstacle)
4. **Increment** the counter when an obstacle is found
5. **Return** the final count after checking all elements

---

## 🔑 Key Concepts

- Basic array iteration
- Conditional statements
- Increment operators
- Array searching techniques

---

## 📚 Example

### Input:
```javascript
river = [0, 1, 0, 1, 1, 0, 1, 0]
```

### Process:
- Position 0: `0` → Clear path
- Position 1: `1` → **Obstacle** (count: 1)
- Position 2: `0` → Clear path
- Position 3: `1` → **Obstacle** (count: 2)
- Position 4: `1` → **Obstacle** (count: 3)
- Position 5: `0` → Clear path
- Position 6: `1` → **Obstacle** (count: 4)
- Position 7: `0` → Clear path

### Output:
```javascript
4
```

---

## ✅ Requirements

- Use basic array searching techniques
- Implement increment operators
- Handle arrays of any length
- Count only elements with value `1`

---

## 🎓 Learning Objectives

By completing this challenge, you will practice:

- ✓ Array traversal and iteration
- ✓ Conditional logic implementation
- ✓ Variable initialization and manipulation
- ✓ Problem-solving with basic data structures

---

**Good luck with your coding challenge! 🚀**
