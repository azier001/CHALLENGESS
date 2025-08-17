# 🐑 Shepherd's Path Counter

## 📊 Challenge Overview

| Difficulty | Level |
|------------|-------|
| **Easy** | ⭐ |

---

## 🎯 Objective

Create a function named `countShepherdMoves` that calculates the number of moves a shepherd makes while traversing through a field containing sheep and dusty spots.

## 📝 Problem Description

The shepherd moves through a field represented as a string, where:
- Each `'s'` represents a **sheep** 🐑
- Each `'.'` represents a **dusty spot** 🌫️

The shepherd makes a move whenever there's a transition between:
- Sheep to dusty spot (`'s'` → `'.'`)
- Dusty spot to sheep (`'.'` → `'s'`)

## 🔧 Function Specification

```javascript
function countShepherdMoves(field) {
    // Your implementation here
}
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `field` | `string` | A string representing the field containing sheep (`'s'`) and dusty spots (`'.'`) |

### Return Value

- **Type**: `integer`
- **Description**: Total number of moves made by the shepherd

## 💡 Examples

```javascript
// Example 1: Simple alternating pattern
countShepherdMoves("s.s.s") 
// Returns: 4 moves
// Transitions: s→. → .→s → s→. → .→s

// Example 2: Consecutive same characters
countShepherdMoves("sss...") 
// Returns: 1 move
// Transitions: s→.

// Example 3: No transitions
countShepherdMoves("ssss") 
// Returns: 0 moves
// No character changes
```

## 🔍 Key Points to Remember

- ✅ Count transitions between different adjacent characters
- ✅ Consecutive same characters don't count as moves
- ✅ Empty string should return 0
- ✅ Single character string should return 0

## 🧠 Approach Hints

1. **Iterate through the string** comparing adjacent characters
2. **Count changes** from one character type to another
3. **Handle edge cases** like empty or single-character strings

---

*Good luck with your implementation! 🚀*
