
# 🌿 Garden Maintenance Challenge

### 🧩 Difficulty: Easy

---

## 📋 Description

Create a function named `maintainGarden` that simulates garden maintenance by **watering plants** and **trimming hedges**.

---

## 🛠️ Function Signature

```javascript
function maintainGarden(gardenBed, hedge)
```

---

## 🧪 Parameters

| Parameter   | Type   | Description                                            |
|-------------|--------|--------------------------------------------------------|
| `gardenBed` | string | `'w'` for watered plants, `'d'` for dry plants. Replace `'d'` with `'w'`. |
| `hedge`     | string | `'g'` for trimmed sections, `'u'` for untrimmed sections. Reverse `'u'` substrings. |

---

## 🔄 Behavior

### 🌱 Garden Bed

- Dry plants (`'d'`) must be watered — replace **every `'d'` with `'w'`**.

### ✂️ Hedge

- Untrimmed sections (`'u'`) must be reversed.  
  Example: `'guuuugg'` → reversed `'uuu'` parts → `'guuuugg'` → `'guuuugg'` (if `'u'` substrings are processed).

> **Note**: Reverse only the continuous substrings of `'u'`.

---

## 📤 Return

An array with **two elements**:

1. The **fully watered** garden bed string.
2. The **neatly trimmed** hedge string.

---

## ✅ Example

```javascript
maintainGarden("dwdwd", "guuugguu")
// ➞ ["wwwww", "guuuggug"]
```

---

## 🌟 Notes

- Use regular expressions or string manipulation for efficient implementation.
- Focus on **clean and readable** code for better maintainability.

---
