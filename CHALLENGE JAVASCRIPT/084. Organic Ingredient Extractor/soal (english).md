# 🌿 Organic Ingredient Extractor

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that filters and extracts organic ingredients from a given list of ingredients.

---

## 🎯 Objective

Implement a function named `getOrganicIngredients` that processes a string of ingredients and returns only those that are marked as organic.

## 📝 Function Specification

### Function Name
```javascript
getOrganicIngredients(ingredientsList)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `ingredientsList` | `string` | A list of ingredients separated by comma and space |

### Return Value

- **Type:** `string`
- **Description:** Organic ingredients separated by comma and space
- **Edge Case:** Returns empty string if no organic ingredients found

---

## 🔍 Requirements

### ✅ Core Logic

1. **Split** the `ingredientsList` string into an array
2. **Filter** ingredients that start with "organic"
3. **Collect** matching ingredients into a new array
4. **Join** the results with comma and space separator
5. **Return** the final string

### 📋 Input/Output Format

- **Input Format:** `"ingredient1, ingredient2, organic ingredient3, ..."`
- **Output Format:** `"organic ingredient3, organic ingredient4, ..."`
- **Empty Result:** `""` (empty string)

---

## 💡 Implementation Hints

- Use string methods like `split()` to convert string to array
- Check if each ingredient starts with the word "organic"
- Consider case sensitivity when checking for "organic" prefix
- Use array methods to filter and join results
- Handle edge cases where no organic ingredients exist

---

## 🧪 Example Test Cases

```javascript
// Example 1: Mixed ingredients
getOrganicIngredients("flour, organic tomatoes, sugar, organic lettuce")
// Expected: "organic tomatoes, organic lettuce"

// Example 2: No organic ingredients
getOrganicIngredients("flour, sugar, salt")
// Expected: ""

// Example 3: All organic ingredients
getOrganicIngredients("organic flour, organic sugar, organic salt")
// Expected: "organic flour, organic sugar, organic salt"
```

---

## 🏆 Success Criteria

Your function should:
- ✅ Correctly identify ingredients starting with "organic"
- ✅ Maintain the original format of organic ingredients
- ✅ Return results in the specified format
- ✅ Handle empty results gracefully
- ✅ Process the input string accurately

---

*Happy coding! 🚀*
