# 🏕️ Pitching a Tent: Army Recruit Training Simulation

## 📋 Challenge Overview
**Difficulty Level:** `Easy`

Create a function that simulates an army recruit's attempt to pitch a tent during basic training. The recruit must navigate through various steps while managing their patience and limited attempts.

---

## 🎯 Objective

Implement a function named `pitchTent` that processes a series of tent-pitching steps while handling different scenarios based on the recruit's patience and available attempts.

---

## 📝 Function Specification

### Function Signature
```javascript
function pitchTent(steps, patience, attempts)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `steps` | `Array<string>` | An array of strings representing the steps to pitch a tent |
| `patience` | `Number` | An integer representing the recruit's initial patience level |
| `attempts` | `Number` | An integer representing the number of allowed attempts |

### Return Value
- **Type:** `String`
- **Success:** `"Tent pitched successfully!"`
- **Failure:** `"Failed to pitch the tent!"`

---

## ⚙️ Implementation Logic

The function must implement the following behavior:

### 🔄 Step Processing
1. **Iterate** through each step in the `steps` array
2. **Analyze** each step for specific keywords:
   - 🔴 **"difficult"** → Decrease `patience` by 1
   - 🟢 **"easy"** → Skip the step (use array slicing)
   - ⚪ **Neither** → Continue to next step (use `continue` statement)

### 🛑 Termination Conditions
- **Stop immediately** if:
  - `patience` reaches `0`, OR
  - All `attempts` are exhausted
- Use `break` statement to exit the loop

### ✅ Success Criteria
- Return success message if **all steps are completed** before running out of patience or attempts
- Otherwise, return failure message

---

## 🚀 Expected Behavior

```javascript
// Example usage scenarios:

// Scenario 1: Successful completion
pitchTent(["setup ground", "easy assembly", "difficult knots"], 2, 3)
// Expected: "Tent pitched successfully!"

// Scenario 2: Patience exhausted
pitchTent(["difficult start", "difficult middle", "difficult end"], 1, 5)
// Expected: "Failed to pitch the tent!"
```

---

## 💡 Key Programming Concepts

- **Array iteration** and processing
- **String manipulation** and keyword detection
- **Conditional logic** with multiple branches
- **Loop control** using `break` and `continue`
- **Array slicing** for step skipping
- **State management** (patience and attempts tracking)

---

## 🎖️ Training Notes

> This simulation reflects real military training scenarios where recruits must:
> - Follow precise procedures under pressure
> - Manage limited resources (time, patience, attempts)
> - Adapt to varying difficulty levels
> - Complete tasks successfully despite obstacles

**Good luck, recruit! 🫡**
