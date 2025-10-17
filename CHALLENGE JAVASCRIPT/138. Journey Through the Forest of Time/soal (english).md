# 🌲 Journey Through the Forest of Time

## Challenge Overview

**Difficulty:** `Easy`

Embark on a mystical journey through a forest of ancient blue-tinged conifers, where each tree holds the wisdom of ages. Your mission is to traverse this enchanted woodland, collecting the stories of time as you go.

---

## 📋 Task Description

Create a function named **`forestJourney`** that calculates the sum of tree ages encountered along your path through the forest.

### Function Signature

```javascript
function forestJourney(forest, startCoordinate)
```

---

## 🎯 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `forest` | `Array<Array<number>>` | A 2D array representing the forest, where each cell contains the age of a tree |
| `startCoordinate` | `Array<number>` | Starting position in format `[row, column]` |

---

## 🎁 Return Value

- **Type:** `number`
- **Description:** The sum of all tree ages encountered during the journey from start to finish

---

## 🧭 Journey Rules

> **Movement Restrictions:**
> - ✅ You can move **RIGHT** (→)
> - ✅ You can move **DOWN** (↓)
> - ❌ You cannot move left or up

> **Path Constraints:**
> - 🚀 Journey starts at `startCoordinate`
> - 🏁 Journey ends at the **bottom-right corner** of the forest
> - 📍 Include the tree age at **both** starting and ending points in your sum

---

## 💡 Example

### Forest Map

```javascript
const forest = [
    [5, 3, 4],
    [2, 1, 7],
    [8, 6, 9]
];

const startCoordinate = [0, 1];  // Starting from the second tree in the first row
```

### Visual Representation

```
    0   1   2
  ┌───┬───┬───┐
0 │ 5 │ 3*│ 4 │  * = Starting Point
  ├───┼───┼───┤
1 │ 2 │ 1 │ 7 │
  ├───┼───┼───┤
2 │ 8 │ 6 │ 9■│  ■ = Ending Point
  └───┴───┴───┘
```

### Sample Path

One possible journey path:

```
3 → 4 → 7 → 9
```

**Result:** `3 + 4 + 7 + 9 = 23`

---

## 🎨 Implementation Note

Your task is to implement the `forestJourney` function that:
1. Navigates through the mystical forest
2. Calculates the sum of tree ages along the path
3. Returns the total sum representing your contemplative journey through time

---

## 🌟 Good Luck!

May your journey through the Forest of Time be filled with wisdom and discovery! 🌲✨
