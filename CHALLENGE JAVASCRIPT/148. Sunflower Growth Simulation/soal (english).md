# 🌻 Sunflower Growth Simulation

## Challenge Overview

**Difficulty:** `Easy`

---

## 📖 Story

Imagine you're on a leisurely ramble through a sunflower field on a breezy afternoon. You've been tasked with monitoring the growth of sunflowers over time. Your function will simulate this growth based on the sunflowers' positions in the field.

---

## 🎯 Objective

Create a function named **`sunflowerHeights`** that simulates the growth of sunflowers over a specified number of days.

---

## 📋 Function Specification

### Function Name
```
sunflowerHeights
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `initialHeights` | `array` | An array of integers representing the initial heights of sunflowers in centimeters |
| `days` | `number` | An integer representing the number of days to simulate growth |

### Return Value

- **Type:** `array`
- **Description:** An array of integers representing the heights of the sunflowers after the specified number of days have passed

---

## 🌱 Growth Pattern Rules

The sunflowers grow according to their position in the field:

- **Even indices** (0, 2, 4, etc.) → Grow by **1 cm** each day
- **Odd indices** (1, 3, 5, etc.) → Grow by **2 cm** each day

---

## 💡 Example

### Input
```javascript
initialHeights = [10, 15, 20, 25]
days = 3
```

### Growth Breakdown

| Day | Index 0 | Index 1 | Index 2 | Index 3 |
|-----|---------|---------|---------|---------|
| 0 (Initial) | 10 cm | 15 cm | 20 cm | 25 cm |
| 1 | 11 cm | 17 cm | 21 cm | 27 cm |
| 2 | 12 cm | 19 cm | 22 cm | 29 cm |
| 3 | 13 cm | 21 cm | 23 cm | 31 cm |

### Output
```javascript
[13, 21, 23, 31]
```

---

## 🔑 Key Points

- Sunflowers at **even positions** grow **slower** (1 cm/day)
- Sunflowers at **odd positions** grow **faster** (2 cm/day)
- Growth is applied cumulatively over the specified number of days
- The original array should be updated with new heights

---

## ✅ Implementation Checklist

- [ ] Create function with correct name and parameters
- [ ] Iterate through the specified number of days
- [ ] Apply correct growth rate based on index position
- [ ] Return updated heights array
- [ ] Test with various input cases

---

**Good luck with your sunflower field simulation! 🌻**
