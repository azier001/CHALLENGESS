
# 🌸 `createFleeceflowerPattern` Function Documentation

## Overview

The `createFleeceflowerPattern` function generates a simplified **binary representation of a floral pattern**, inspired by **fleeceflower blossoms**. This pattern is displayed using alternating `1`s and `0`s arranged in a symmetric, flower-like shape.

---

## ✨ Features

- Centered symmetrical pattern
- Alternating binary values (`1`, `0`, `1`, ...)
- Expands and contracts to simulate flower petals
- Each row is properly aligned with spaces
- Ideal for console-based visual displays

---

## 🧾 Function Signature

```javascript
function createFleeceflowerPattern(size)
```

---

## 📥 Parameters

| Parameter | Type   | Description                              |
|-----------|--------|------------------------------------------|
| `size`    | number | An **odd integer ≥ 3**. Represents the number of rows in the pattern. |

> ⚠️ The `size` must be an **odd number** and **at least 3** for the pattern to form correctly.

---

## 📤 Returns

- A `string` representing the floral pattern.
- Each row is separated by a newline character (`\n`).
- Each line is padded with spaces to maintain symmetry.

---

## 🧮 Pattern Explanation

For `size = 5`, the output is:

```
  1  
 101 
10101
 101 
  1  
```

### Characteristics:

- The pattern has a **vertical and horizontal symmetry**.
- The **center row** is the widest, containing the most digits.
- Binary digits alternate in each row: starting from `1`, then `0`, then `1`, and so on.
- The shape gradually **expands** from the top, peaks at the center, and then **contracts** at the bottom.

---

## 🛠️ Example Usage

```javascript
console.log(createFleeceflowerPattern(5));
```

**Output:**
```
  1  
 101 
10101
 101 
  1  
```

---

## 📌 Notes

- Use basic **loops** and **string concatenation** to construct each row.
- The number of digits in each row should follow the pattern:
  - From top to center: `1, 3, 5, ...`
  - From center to bottom: symmetric to the top

---

## 🧑‍💻 Implementation Hint

A good strategy to build the pattern:

1. Loop from `0` to `size - 1`.
2. Use `Math.min(i, size - 1 - i)` to determine how wide each row should be.
3. Use alternating binary characters starting with `1`.
4. Pad the row with spaces to center it.

---
