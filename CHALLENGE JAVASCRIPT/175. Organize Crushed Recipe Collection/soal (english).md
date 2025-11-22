# 📚 Organize Crushed Recipe Collection

## Challenge Overview

**Difficulty Level:** `Easy` 🟢

Your grandmother's cherished recipe collection has been damaged and needs organizing! Help restore order by creating a system that groups recipes by type and ensures all recipes have proper cooking times.

---

## 🎯 Objective

Write a function called `organizeRecipes` that processes a collection of recipes and organizes them into a structured format by recipe type.

---

## 📋 Function Specification

### Function Name
```javascript
organizeRecipes(recipes)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `recipes` | `Array<Object>` | Array of recipe objects containing recipe information |

#### Recipe Object Structure

Each recipe object contains the following properties:

- **`name`** *(string)* - The name of the recipe
- **`type`** *(string)* - The category/type of the recipe (e.g., "dessert", "main", "appetizer")
- **`cookingTime`** *(number, optional)* - Cooking time in minutes

---

## 🔄 Processing Rules

The function must perform two key operations:

1. **Set Default Cooking Time**: If a recipe is missing the `cookingTime` property, automatically set it to **30 minutes**
2. **Group by Type**: Organize recipes by their `type`, collecting all recipe names under each category

---

## 📤 Return Value

**Type:** `Object`

Returns an object where:
- **Keys** are recipe types (strings)
- **Values** are arrays of recipe names (array of strings)

### Return Format Example

```javascript
{
  "dessert": ["Chocolate Cake", "Apple Pie"],
  "main": ["Beef Stew"],
  "appetizer": ["Caesar Salad"]
}
```

---

## 💡 Example Usage

### Input
```javascript
const recipes = [
  { name: "Chocolate Cake", type: "dessert", cookingTime: 45 },
  { name: "Apple Pie", type: "dessert" },
  { name: "Beef Stew", type: "main", cookingTime: 120 },
  { name: "Caesar Salad", type: "appetizer" }
];

organizeRecipes(recipes);
```

### Expected Output
```javascript
{
  "dessert": ["Chocolate Cake", "Apple Pie"],
  "main": ["Beef Stew"],
  "appetizer": ["Caesar Salad"]
}
```

> **Note:** "Apple Pie" and "Caesar Salad" had missing cooking times, which were automatically set to 30 minutes during processing (though this doesn't affect the output structure).

---

## ✅ Key Requirements

- ✓ Handle recipes with missing `cookingTime` values
- ✓ Group recipes by their `type` property
- ✓ Maintain all recipe names within their respective type arrays
- ✓ Return a properly structured object

---

## 🚀 Getting Started

Begin by considering:
1. How to iterate through the recipe array
2. How to check for missing properties and set defaults
3. How to build and populate the result object dynamically
4. The best data structure approach for grouping items

Good luck organizing the recipe collection! 👩‍🍳👨‍🍳
