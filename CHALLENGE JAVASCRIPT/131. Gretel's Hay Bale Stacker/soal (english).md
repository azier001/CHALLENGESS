# 🌾 Gretel's Hay Bale Stacker

## Challenge Overview

**Difficulty Level:** `Easy`

---

## 📖 Story

Gretel, a farm girl, is stacking hay bales in her rustic barn. Your task is to help her organize the hay bales into a neat, comma-separated list.

---

## 🎯 Objective

Create a function named **`stackHayBales`** that adds a new hay bale to the current stack and returns a beautifully formatted string representation of all the hay bales.

---

## 🔧 Function Specification

### Function Name
```javascript
stackHayBales(currentStack, newBale)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `currentStack` | `array` | An array of strings representing the current stack of hay bales |
| `newBale` | `string` | A string representing a new hay bale to be added to the stack |

### Return Value

- **Type:** `string`
- **Format:** All hay bales in the stack, separated by commas, with "and" before the last hay bale

---

## 📋 Requirements

1. Add the `newBale` to the end of the `currentStack`
2. Format the output as a single string with:
   - Commas separating the hay bales
   - The word "and" before the last hay bale
3. Return the formatted string

---

## 💡 Example Format

If the stack contains `["Bale A", "Bale B", "Bale C"]`, the output should be:

```
Bale A, Bale B, and Bale C
```

---

## ✨ Tips

- Think about edge cases: What if there's only one bale? Two bales?
- Consider how to properly join array elements with the correct punctuation
- Remember to add the new bale before formatting the output

---

**Happy Coding! 🚜**
