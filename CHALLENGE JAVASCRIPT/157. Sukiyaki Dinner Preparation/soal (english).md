# 🍲 Sukiyaki Dinner Preparation Challenge

## Difficulty Level
**Easy** 🟢

---

## 📋 Challenge Description

Create a function named `prepareSukiyaki` that receives `meats` and `vegetables` as parameters.

This function combines ingredients from both arrays into a single array, **alternating between one meat and one vegetable**, starting with meat.

---

## 🎯 Function Signature

```javascript
prepareSukiyaki(meats, vegetables)
```

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `meats` | `array of strings` | Sliced meats for the sukiyaki |
| `vegetables` | `array of strings` | Vegetables for the sukiyaki |

---

## 📤 Return Value

Returns an **array of strings** representing the order of ingredients added to the pot.

---

## 💡 Key Requirements

- ✅ Alternate between meat and vegetable
- ✅ Start with meat first
- ✅ Combine both arrays into a single result

---

## 📝 Example

```javascript
const meats = ["beef", "pork", "chicken"];
const vegetables = ["tofu", "mushroom", "cabbage"];

prepareSukiyaki(meats, vegetables);
// Expected output: ["beef", "tofu", "pork", "mushroom", "chicken", "cabbage"]
```

---

## 🧠 Hints

- Think about how to iterate through both arrays simultaneously
- Consider what happens when one array is longer than the other
- The pattern should be: meat → vegetable → meat → vegetable...

---

## 🎉 Good luck with your sukiyaki preparation!
