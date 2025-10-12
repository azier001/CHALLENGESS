# 🗺️ Navigate Fiords Challenge

## Difficulty Level
**Easy** ⭐

---

## 📋 Challenge Description

Create a function that navigates through the fiords based on directional commands. Your task is to implement a navigation system that processes an array of directions and determines the final destination.

---

## 🎯 Function Specification

### Function Name
```javascript
navigateFiords(directions, startingPoint)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `directions` | `Array<string>` | An array containing navigation directions |
| `startingPoint` | `number` | The initial position index (where `'start'` is located in the array) |

---

## 🧭 Navigation Rules

Use a **`switch` statement** to handle each direction:

| Direction | Action | Condition |
|-----------|--------|-----------|
| **`'north'`** | Move to the **previous** element | Only if not at the start of the array |
| **`'south'`** | Move to the **next** element | Only if not at the end of the array |
| **`'east'`** | **Remain** at the current position | Always valid |
| **`'west'`** | Move **two elements forward** | Only if not exceeding the array length |

---

## ✅ Return Value

- **Success**: Return the destination value reached after following all directions
- **Failure**: Return `'lost'` if navigation goes beyond array boundaries at any point

---

## 💡 Example Scenarios

### Example 1: Successful Navigation
```javascript
const directions = ['start', 'north', 'checkpoint', 'south', 'end'];
const startingPoint = 0;
// Process: start → follow directions → arrive at destination
```

### Example 2: Lost Navigation
```javascript
const directions = ['start', 'north', 'south'];
const startingPoint = 0;
// Process: start → try to go north (out of bounds) → return 'lost'
```

---

## 🔑 Key Points

- ⚠️ **Boundary Checking**: Always validate if the move is within array bounds
- 🔄 **Switch Statement**: Must use a switch statement for direction handling
- 📍 **Starting Point**: Begin navigation at the `startingPoint` index
- 🚫 **Early Exit**: Return `'lost'` immediately if any move goes out of bounds

---

## 🚀 Getting Started

Think about:
1. How to track your current position in the array
2. How to validate moves before executing them
3. When to return `'lost'` vs. the destination value
4. How to iterate through the navigation process

Good luck with your fiords navigation! 🏔️
