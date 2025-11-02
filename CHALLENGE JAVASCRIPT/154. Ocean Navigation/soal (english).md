# 🌊 Ocean Navigation Challenge

## Difficulty Level
**Easy** ⭐

---

## 📋 Challenge Description

Create a function named `navigateOcean` that determines if a ship can travel directly from its current position to a destination on a grid-based ocean map.

---

## 🗺️ Grid System

The ocean is represented as a **5×5 grid** where each position is identified by:

- **Letter (A-E)**: Vertical position (rows)
- **Number (1-5)**: Horizontal position (columns)

### Grid Layout Example

```
    1   2   3   4   5
  ┌───┬───┬───┬───┬───┐
A │ A1│ A2│ A3│ A4│ A5│
  ├───┼───┼───┼───┼───┤
B │ B1│ B2│ B3│ B4│ B5│
  ├───┼───┼───┼───┼───┤
C │ C1│ C2│ C3│ C4│ C5│
  ├───┼───┼───┼───┼───┤
D │ D1│ D2│ D3│ D4│ D5│
  ├───┼───┼───┼───┼───┤
E │ E1│ E2│ E3│ E4│ E5│
  └───┴───┴───┴───┴───┘
```

---

## 🎯 Navigation Rules

The ship can travel **directly** if it moves along:

- ✅ **Same horizontal line** (same number) — *Example: A1 → E1*
- ✅ **Same vertical line** (same letter) — *Example: A1 → A5*

The ship **cannot** travel directly if:

- ❌ **Both letter AND number change** — *Example: A1 → B3*

---

## 📝 Function Specification

### Function Signature

```javascript
function navigateOcean(currentPosition, destination)
```

### Parameters

| Parameter | Type | Description | Example |
|-----------|------|-------------|---------|
| `currentPosition` | `string` | The ship's current position on the grid | `"A1"` |
| `destination` | `string` | The desired destination position | `"B3"` |

### Return Value

| Type | Value | Condition |
|------|-------|-----------|
| `boolean` | `true` | Direct travel is **possible** (same row OR same column) |
| `boolean` | `false` | Direct travel is **not possible** (diagonal movement) |

---

## 💡 Examples

### ✅ Valid Direct Travels

```javascript
navigateOcean("A1", "A5")  // true  → Same row (A)
navigateOcean("B2", "E2")  // true  → Same column (2)
navigateOcean("C3", "C3")  // true  → Same position
```

### ❌ Invalid Direct Travels

```javascript
navigateOcean("A1", "B3")  // false → Different row AND column
navigateOcean("D2", "E4")  // false → Diagonal movement
navigateOcean("A1", "E5")  // false → Diagonal movement
```

---

## 🚀 Implementation Tips

1. Extract the **letter** (vertical) and **number** (horizontal) from each position
2. Compare both components between current position and destination
3. Return `true` if **either** the letter **or** the number matches (or both)
4. Return `false` if **both** are different

---

## 🎓 Skills Practiced

- String manipulation
- Conditional logic
- Boolean operations
- Pattern recognition

---

**Good luck, Captain!** ⚓
