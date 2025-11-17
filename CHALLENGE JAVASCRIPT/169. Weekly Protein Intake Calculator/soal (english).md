# 🥗 Weekly Protein Intake Calculator

## Challenge Overview

**Difficulty Level:** `Medium` 🟡

---

## 📋 Description

Write a function `calculateDailyProtein` that processes a weekly meal plan grid and calculates the total protein content for each day of the week.

The function analyzes a 7-day meal plan where each day contains up to 4 meals, computing daily protein totals while treating missing meals (represented as `-1`) as 0 protein.

---

## 🎯 Function Requirements

### Function Signature

```javascript
function calculateDailyProtein(mealPlan)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `mealPlan` | `Array<Array<number>>` | A **7×4** 2D array where:<br>• Each **row** represents one day (7 days total)<br>• Each **column** represents a meal (4 meals per day)<br>• Values are protein amounts in grams<br>• `-1` indicates no meal planned |

### Returns

**Type:** `Array<number>`

An array of 7 integers representing the total daily protein intake for each day of the week.

**Format:** `[day1Total, day2Total, day3Total, day4Total, day5Total, day6Total, day7Total]`

---

## 🧠 Logic Breakdown

The function should follow these steps:

1. **Iterate through each day** (row) in the meal plan
2. **For each day**, sum all meal protein values in that row
3. **Replace any `-1` values** with `0` before summing
4. **Store the daily total** and continue to the next day
5. **Return the array** of all 7 daily totals

---

## 💡 Example

### Input

```javascript
const mealPlan = [
  [30, 25, -1, 40],  // Day 1
  [20, 30, 35, -1],  // Day 2
  [25, -1, 30, 35],  // Day 3
  [-1, 40, 25, 30],  // Day 4
  [35, 30, -1, 25],  // Day 5
  [30, 25, 40, -1],  // Day 6
  [20, -1, 35, 30]   // Day 7
];
```

### Output

```javascript
[95, 85, 90, 95, 90, 95, 85]
```

### Explanation

- **Day 1:** 30 + 25 + 0 + 40 = **95g**
- **Day 2:** 20 + 30 + 35 + 0 = **85g**
- **Day 3:** 25 + 0 + 30 + 35 = **90g**
- **Day 4:** 0 + 40 + 25 + 30 = **95g**
- **Day 5:** 35 + 30 + 0 + 25 = **90g**
- **Day 6:** 30 + 25 + 40 + 0 = **95g**
- **Day 7:** 20 + 0 + 35 + 30 = **85g**

---

## ✅ Key Points to Remember

- ⚠️ Missing meals are marked as `-1` and should be counted as `0` protein
- 📊 Each day has exactly 4 meal slots (some may be `-1`)
- 🔢 The input is always a 7×4 grid (7 days, 4 meals per day)
- 📤 Return an array with exactly 7 elements (one per day)

---

## 🚀 Implementation Tips

- Use array methods like `map()` and `reduce()` for cleaner code
- Handle `-1` values by replacing them with `0` during summation
- Consider using conditional logic or `Math.max()` to handle negative values
- Test edge cases where all meals are `-1` for a given day

---

**Good luck with your implementation!** 💪
