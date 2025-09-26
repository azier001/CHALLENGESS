# 🍽️ Family Gathering Meal Cost Calculator

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function that calculates the total cost for meals at a family gathering based on guest count and meal preferences.

---

## 🎯 Objective

Implement a function named `calculateMealCost` that computes the total meal cost for a family gathering event.

## 📝 Function Specification

### Function Name
```javascript
calculateMealCost(guestCount, mealType)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `guestCount` | `number` | Total number of guests attending |
| `mealType` | `string` | Type of meal: `"vegetarian"` or `"non-vegetarian"` |

### Return Value

- **Type:** `number`
- **Description:** Total cost for all meals

---

## 💰 Pricing Structure

| Meal Type | Cost per Person |
|-----------|----------------|
| 🥗 **Vegetarian** | `$10` |
| 🍖 **Non-Vegetarian** | `$15` |

---

## 🔧 Implementation Requirements

1. **Function Logic:**
   - Determine cost per person based on `mealType`
   - Multiply cost per person by `guestCount`
   - Return the total calculated cost

2. **Calculation Formula:**
   ```
   Total Cost = Cost per Person × Guest Count
   ```

---

## 💡 Example Usage

```javascript
// Vegetarian meal for 8 guests
calculateMealCost(8, "vegetarian");
// Expected result: 80

// Non-vegetarian meal for 12 guests  
calculateMealCost(12, "non-vegetarian");
// Expected result: 180
```

---

## ✅ Success Criteria

- [ ] Function accepts two parameters correctly
- [ ] Properly handles vegetarian pricing ($10/person)
- [ ] Properly handles non-vegetarian pricing ($15/person)
- [ ] Returns accurate total cost calculation
- [ ] Function name matches specification exactly

---

*Good luck with your implementation! 🚀*
