# 🌲 Forest Path Clearing Simulation

## 📋 Challenge Overview

**Difficulty:** `Easy`

Create a function that simulates a gardener clearing paths through a forest in a spiral pattern. The gardener moves through the forest and clears a 3×3 area around their position at each step.

---

## 🎯 Objective

Implement the `clearForestPaths` function that receives four parameters and returns a modified 2D array representing the forest after the gardener completes all clearing steps.

---

## 📥 Function Signature

```javascript
function clearForestPaths(forest, startRow, startCol, steps)
```

---

## 🔧 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `forest` | `Array<Array<string>>` | A 2D array representing the forest grid |
| `startRow` | `number` | Starting row position (0-indexed) |
| `startCol` | `number` | Starting column position (0-indexed) |
| `steps` | `number` | Number of steps the gardener takes |

---

## 🗺️ Forest Representation

The forest is represented by a 2D array where each cell contains one of three characters:

- **`'T'`** - Tree (can be cleared)
- **`'P'`** - Path (already cleared)
- **`'C'`** - Clearing (open area)

---

## 🌀 Movement Pattern

The gardener follows a **spiral pattern**:

1. **Right** →
2. **Down** ↓
3. **Left** ←
4. **Up** ↑
5. Repeat...

---

## ✂️ Clearing Mechanism

At each step:

1. **Clear** a 3×3 area centered on the current position
2. Replace all `'T'` (trees) with `'P'` (paths) in this area
3. **Move** to the next position following the spiral pattern

### 3×3 Clearing Area

```
[ ][ ][ ]
[ ][G][ ]  ← G = Gardener position
[ ][ ][ ]
```

---

## ⚠️ Important Constraints

- **Boundary handling:** Do not modify positions outside the forest boundaries
- If the 3×3 area extends beyond the edges, only clear valid positions within the forest
- Only `'T'` cells should be converted to `'P'`
- `'P'` and `'C'` cells remain unchanged

---

## 📤 Return Value

Returns the modified 2D array (`Array<Array<string>>`) representing the forest after all clearing steps are completed.

---

## 💡 Example Scenario

**Initial Forest:**
```
T T T T T
T T T T T
T T T T T
T T T T T
```

**After clearing from position (1, 1) with 2 steps:**
```
T P P P T
T P P P T
T P P T T
T T T T T
```

---

## 🎓 Tips

- Track the current direction (right, down, left, up)
- Change direction after moving in the spiral pattern
- Use boundary checks before clearing each cell in the 3×3 area
- Consider edge cases where the starting position is near boundaries

---

**Good luck with your implementation! 🚀**
