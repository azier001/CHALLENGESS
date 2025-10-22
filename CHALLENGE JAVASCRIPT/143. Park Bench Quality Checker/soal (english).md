# 🪑 Park Bench Quality Checker

> **Difficulty Level:** `Easy` 🟢

---

## 📋 Challenge Overview

The local parks department is facing criticism due to poorly maintained benches. Your task is to create a function that evaluates the quality of park benches based on their coating thickness and location.

---

## 🎯 Objective

Create a function named **`benchQualityChecker`** that assesses park bench quality and provides maintenance recommendations.

---

## 📥 Function Parameters

The function should accept **two parameters**:

| Parameter | Type | Description |
|-----------|------|-------------|
| `coatingThickness` | `number` | An integer representing the coating thickness in **micrometers (μm)** |
| `isHighTraffic` | `boolean` | Indicates if the bench is in a high-traffic area (`true`) or low-traffic area (`false`) |

---

## 🔍 Quality Assessment Criteria

The function should return a string based on the following evaluation rules:

### 🔴 Critical Condition
- **Coating < 50 μm**
  - Return: `"Terrible - Replace immediately!"`

### 🟡 Warning Conditions
- **Coating: 50-100 μm (inclusive)**
  - **High-traffic area:** Return `"Poor - Needs recoating soon"`
  - **Low-traffic area:** Return `"Acceptable - Monitor closely"`

### 🟢 Good Condition
- **Coating: 101-150 μm (inclusive)**
  - Return: `"Good - No action needed"`

### 🔵 Excessive Coating
- **Coating > 150 μm**
  - Return: `"Excellent - Overcoated!"`

---

## 💡 Implementation Requirements

- Use **conditional statements** (`if-else`) to implement the logic
- Ensure proper handling of **boundary values** (50, 100, 101, 150)
- Consider **both parameters** when evaluating benches in the 50-100 μm range

---

## 📝 Function Signature

```javascript
function benchQualityChecker(coatingThickness, isHighTraffic) {
  // Your implementation here
}
```

---

## ✅ Expected Behavior Examples

```javascript
// Critical case
benchQualityChecker(45, false)
// → "Terrible - Replace immediately!"

// Warning cases
benchQualityChecker(75, true)
// → "Poor - Needs recoating soon"

benchQualityChecker(75, false)
// → "Acceptable - Monitor closely"

// Good case
benchQualityChecker(125, true)
// → "Good - No action needed"

// Excessive coating
benchQualityChecker(200, false)
// → "Excellent - Overcoated!"
```

---

## 🚀 Getting Started

1. Define the function with the required parameters
2. Implement the conditional logic following the criteria above
3. Test with various input combinations
4. Ensure all edge cases are covered

---

**Good luck! 🎉**
