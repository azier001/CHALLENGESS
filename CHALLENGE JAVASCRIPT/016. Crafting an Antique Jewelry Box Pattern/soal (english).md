
# 💍 **Antique Jewelry Box Pattern Generator**

## 📦 Overview
The `createAntiqueJewelryBox` function generates a **square ASCII pattern** that resembles an antique jewelry box with multiple decorative layers. The box is made of `*` (asterisks) and `.` (dots), representing outer casing and ornate compartments.

Each layer symbolizes a level of ornamentation—starting from the outermost border toward the minimalistic inner chamber.

---

## 🧾 Function Signature

```javascript
function createAntiqueJewelryBox(layers)
```

---

## 📥 Parameters

| Parameter | Type   | Description                                         |
|-----------|--------|-----------------------------------------------------|
| `layers`  | number | A non-negative integer (`≥ 0`) representing the number of decorative layers. |

---

## 📤 Returns

- A single `string` representing the layered jewelry box pattern.
- Each line of the pattern is separated by a newline character (`\n`).

---

## 🧮 Pattern & Rules

- 🧱 **Box size** = `2 * layers + 3` (height and width).
- ✨ **Outermost layer** is filled completely with `*`.
- 🎨 **Inner layers**:
  - Corners contain `*`
  - Interior contains `.`
- 🧊 **Innermost (core) layer**, if any, contains only `.`.

---

## 📌 Pattern Examples

### 🔢 Input: `2`

```
*******
*.....*
*.*.*.*
*.....*
*******
```

### 🔢 Input: `3`

```
*********
*.......*
*.*****.*
*.*...*.*
*.*...*.*
*.*****.*
*.......*
*********
```

---

## 🛠️ Implementation Tips

- 🧩 Use **nested loops** to build each row.
- 🧮 Construct a matrix of size `N x N`, where `N = 2 * layers + 3`.
- 🔁 Loop through layers:
  - Mark borders with `*`
  - Fill interior with `.` or structured `*` based on depth

---

## 📚 Example Usage

```javascript
console.log(createAntiqueJewelryBox(2));
```
