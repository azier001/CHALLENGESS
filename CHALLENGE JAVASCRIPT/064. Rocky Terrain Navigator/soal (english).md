# 🏔️ Rocky Terrain Navigator

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function that simulates navigating through treacherous rocky terrain filled with obstacles. Your mission is to determine where a navigator will end up after taking a specific number of steps through the challenging landscape.

---

## 🎯 Problem Description

You need to implement a function named `rockyTerrainNavigator` that simulates movement through a 1D terrain represented by an array of strings. The terrain contains two types of elements:

- **"Path"** - Safe ground to walk on
- **"Obstacle"** - Rocky obstacles that cause stumbling

### 🚶‍♂️ Navigation Rules

1. **Starting Position**: Begin at index `0` of the terrain array
2. **Normal Movement**: Each step moves you forward by one position
3. **Obstacle Penalty**: Stepping on an "Obstacle" causes you to stumble and move back one step
4. **Boundary Limit**: If your steps would take you beyond the array's end, you remain at the last element

---

## 📝 Function Specification

### Function Signature
```javascript
rockyTerrainNavigator(terrain, steps)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `terrain` | `Array<String>` | Array representing the terrain path, containing "Path" or "Obstacle" |
| `steps` | `Number` | Number of forward steps the navigator plans to take |

### Return Value

| Type | Description |
|------|-------------|
| `Number` | Final position (index) in the terrain array after navigation |

---

## 💡 Examples

### Example 1: Basic Navigation
```javascript
const terrain = ["Path", "Path", "Obstacle", "Path", "Path"];
const steps = 4;
// Expected result: Navigator ends up at index 3
```

### Example 2: Multiple Obstacles
```javascript
const terrain = ["Path", "Obstacle", "Obstacle", "Path"];
const steps = 3;
// Expected result: Navigator ends up at index 1
```

### Example 3: Exceeding Array Bounds
```javascript
const terrain = ["Path", "Path", "Path"];
const steps = 10;
// Expected result: Navigator ends up at index 2 (last element)
```

---

## 🔍 Key Considerations

- ⚠️ **Stumble Mechanics**: When hitting an obstacle, the navigator moves back one position
- 🛡️ **Boundary Protection**: Prevent navigation beyond the array limits
- 🎯 **Zero-based Indexing**: Remember that array positions start from 0
- 🔄 **Step Counting**: Each forward movement counts as one step, regardless of stumbles

---

## 🎮 Challenge Tips

1. **Track Position**: Keep track of the current position as you iterate through steps
2. **Validate Bounds**: Always check if the next position is within array limits
3. **Handle Obstacles**: Implement the stumble-back logic when encountering obstacles
4. **Edge Cases**: Consider scenarios with consecutive obstacles or very large step counts

---

## 🏆 Success Criteria

Your solution should:
- ✅ Correctly handle normal path navigation
- ✅ Implement obstacle stumbling mechanics
- ✅ Respect array boundaries
- ✅ Return the accurate final position index
- ✅ Handle edge cases gracefully

---

*Good luck navigating through the rocky terrain! 🗻*
