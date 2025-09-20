# 🚤 Peaceful River Boat Simulation

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that simulates the peaceful movement of boats along a flowing river. This challenge combines array manipulation, iteration, and logical thinking to model a dynamic river ecosystem.

---

## 🎯 Function Specification

### Function Name
```javascript
riverBoatSimulation(initialPositions, timeSteps)
```

### Description
The function simulates the movement of boats along a peaceful river where each boat moves downstream at different speeds, and new boats periodically join the journey.

---

## 📐 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `initialPositions` | `Array<number>` | An array of integers representing the initial positions of boats on the river (0 being the starting point) |
| `timeSteps` | `number` | The number of time steps to simulate |

---

## 🔄 Simulation Rules

### Movement Mechanics
- **Each existing boat moves downstream** by incrementing its position
- **Boat speed is determined by its index** in the array plus 1:
  - 1st boat (index 0) → moves 1 unit per step
  - 2nd boat (index 1) → moves 2 units per step  
  - 3rd boat (index 2) → moves 3 units per step
  - And so on...

### New Boat Spawning
- **Every even-numbered step** (including step 0), a new boat joins at position 0
- Even steps: `0, 2, 4, 6, 8, ...`

---

## 📤 Return Value

**Type:** `Array<number>`

Returns an array of integers representing the **final positions of all boats** after completing the simulation.

---

## 💡 Example Walkthrough

```javascript
// Example: riverBoatSimulation([5, 10], 3)

Initial state: [5, 10]
Step 0 (even): Add new boat → [0, 5, 10]
           Move boats → [0, 6, 12]

Step 1 (odd):  No new boat
           Move boats → [1, 8, 15]

Step 2 (even): Add new boat → [0, 1, 8, 15]
           Move boats → [0, 2, 10, 18]

Step 3 (odd):  No new boat  
           Move boats → [1, 4, 13, 22]

Final result: [1, 4, 13, 22]
```

---

## 🧠 Key Concepts

- **Array Manipulation**: Adding and modifying elements
- **Index-based Logic**: Using array indices for speed calculation
- **Conditional Logic**: Even/odd step detection
- **Iteration**: Processing multiple time steps
- **Simulation**: Modeling real-world movement patterns

---

## ✅ Implementation Checklist

- [ ] Handle initial boat positions correctly
- [ ] Implement proper speed calculation (index + 1)
- [ ] Add new boats on even-numbered steps only
- [ ] Move all boats according to their speeds each step
- [ ] Return final positions array
- [ ] Handle edge cases (empty initial array, zero time steps)

---

*Happy coding! 🌊*
