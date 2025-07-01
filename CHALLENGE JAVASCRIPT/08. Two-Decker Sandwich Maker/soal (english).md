# 🥪 Two-Decker Sandwich Maker

## 🧠 Challenge Overview

**Difficulty:** 🟢 Easy  
Create a function named `makeSandwich` that takes three parameters:

- `topBread`
- `filling`
- `bottomBread`

Your goal is to determine if a valid **two-decker sandwich** can be made and return the appropriate message based on the input.

---

## 📜 Sandwich Rules

To make a valid sandwich, follow these criteria:

✅ **Bread Types**
- Both `topBread` and `bottomBread` must be either:
  - `"white"` 🍞
  - `"wheat"` 🌾

✅ **Valid Fillings**
- The filling must be one of the following:
  - `"cheese"` 🧀
  - `"ham"` 🍖
  - `"lettuce"` 🥬

✅ **Bread Matching**
- The `topBread` and `bottomBread` must be the **same type**.

---

## 🔢 Function Parameters

| Parameter     | Type   | Description                                     |
|---------------|--------|-------------------------------------------------|
| `topBread`    | string | The type of top bread (`"white"` or `"wheat"`) |
| `filling`     | string | The sandwich filling (`"cheese"`, `"ham"`, or `"lettuce"`) |
| `bottomBread` | string | The type of bottom bread (`"white"` or `"wheat"`) |

---

## 🧾 Return Messages

Your function should return one of the following messages:

- ✅ **All criteria met:**  
  `"Delicious [filling] sandwich on [bread type] bread!"`

- ❌ **Mismatched bread types:**  
  `"Mismatched bread types!"`

- ❌ **Invalid bread type used:**  
  `"Invalid bread type!"`

- ❌ **Invalid filling used:**  
  `"Invalid filling!"`

---

## ✅ Example

```javascript
makeSandwich("white", "cheese", "white");
// ➜ "Delicious cheese sandwich on white bread!"

makeSandwich("white", "bacon", "white");
// ➜ "Invalid filling!"

makeSandwich("wheat", "ham", "white");
// ➜ "Mismatched bread types!"

makeSandwich("rye", "lettuce", "wheat");
// ➜ "Invalid bread type!"
