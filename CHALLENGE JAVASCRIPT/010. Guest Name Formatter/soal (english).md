# 🎉 Guest Name Formatter

## 📝 Challenge Overview

**Difficulty:** 🟢 Easy

Create a function named `formatGuestNames` that formats a list of guest names into a friendly and grammatically correct greeting.

---

## 📥 Input

A single **comma-separated** string of guest names.

---

## 📤 Output

A **formatted string** suitable for greeting guests, based on the number of names provided.

---

## 🧠 Formatting Rules

| Number of Names | Format Example |
|-----------------|----------------|
| 1 Name          | `Alice` → `Alice` |
| 2 Names         | `Alice,Bob` → `Alice and Bob` |
| 3+ Names        | `Alice,Charlie,Bob` → `Alice, Charlie, and Bob` |

---

## 🛠️ Steps to Solve

1. **Split** the string using `split(",")`.
2. **Check the length** of the resulting array:
   - If **1**, return the name as-is.
   - If **2**, join with `" and "`.
   - If **more than 2**:
     - Join all except the last with `", "`.
     - Append `", and "` followed by the last name.
3. **Return** the final formatted string.

---

## 📦 Parameters

- `guestNames` (`string`): A comma-separated string of guest names.

## ✅ Returns

- `string`: A formatted greeting string.

---

## 🔍 Examples

```javascript
formatGuestNames("Alice") 
// Output: "Alice"

formatGuestNames("Alice,Bob") 
// Output: "Alice and Bob"

formatGuestNames("Alice,Charlie,Bob") 
// Output: "Alice, Charlie, and Bob"
```

---

Happy Coding! 🎊
