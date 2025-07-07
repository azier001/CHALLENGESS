# 🍎 Apple Variety Comparison Challenge

## 📋 Overview
Create a function that simulates a scientist's analysis of apple varieties in an orchard by comparing two apple variety names and calculating their similarity score.

---

## 🎯 Challenge Details

**Difficulty Level:** `Easy`

**Function Name:** `compareApples`

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `variety1` | `string` | The name of the first apple variety |
| `variety2` | `string` | The name of the second apple variety |
| `appleCount` | `number` | The number of apples to compare |

---

## 🔍 Algorithm Requirements

### Character-by-Character Comparison
- Compare the two apple variety names **character by character**
- Increment a counter for each **matching character** at the same position
- If names have different lengths, stop comparison at the end of the **shorter name**

### Similarity Score Calculation
```
Similarity Score = (Matching Characters / Length of Shorter Name) × 100
```

### Rounding
- Round the similarity score to **two decimal places**

---

## 📤 Return Value

The function should return a **string** that includes:
- ✅ Names of both apple varieties
- ✅ Number of apples compared
- ✅ Similarity score (rounded to 2 decimal places)

---

## 💡 Example Usage

```javascript
// Example function call
compareApples("Gala", "Granny", 50);

// Expected output format:
// "Comparing Gala and Granny varieties with 50 apples. Similarity score: 20.00%"
```

---

## 🧪 Scientific Context

This function simulates how agricultural scientists might:
- 🔬 Analyze genetic similarities between apple varieties
- 📊 Compare morphological characteristics
- 🌱 Study breeding compatibility
- 📈 Assess variety classification accuracy

---

## 🎨 Implementation Tips

> **Hint:** Consider using string methods like `.length`, `.charAt()`, or array indexing to access individual characters.

> **Note:** Remember to handle edge cases where one or both strings might be empty.

---

*Happy coding! 🚀*
