# 🎨 Sort Colors with Green First

## 🧩 Challenge Overview

**Level:** 🟢 Easy  
**Goal:** Create a function `sortColors` that sorts color strings **alphabetically**, but moves all `"green"` entries (if any) to the **front** of the array.

---

## ✅ Requirements

- 🔤 Sort all colors **alphabetically**.
- 🥇 If `"green"` exists, place **all occurrences** at the **beginning**.
- 🔁 Multiple `"green"` entries should appear **before** any other color.
- 🔠 Sorting must be **case-sensitive**:
  - `"Green"` and `"green"` are **not** the same.
- 🧪 Input will contain **only valid** color strings.

---

## 📌 Examples

```js
sortColors(["blue", "red", "yellow"]);
// ➞ ["blue", "red", "yellow"]

sortColors(["blue", "green", "red"]);
// ➞ ["green", "blue", "red"]

sortColors(["purple", "orange", "green", "cyan"]);
// ➞ ["green", "cyan", "orange", "purple"]

sortColors(["green", "Green", "green", "blue"]);
// ➞ ["green", "green", "Green", "blue"]
