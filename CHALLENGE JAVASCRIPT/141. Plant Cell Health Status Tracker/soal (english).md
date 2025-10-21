# 🌱 Plant Cell Health Status Tracker

## Challenge Level
**Easy** 🟢

---

## 📋 Overview

Create a function named `checkPlantCellHealth` that monitors the health status of plant cells based on cellular integrity measurements and pest behavior indicators.

---

## 🎯 Objective

The function receives two parameters: `cellIntegrity` and `pestPresence`. It iterates through the `cellIntegrity` array and checks the corresponding value in the `pestPresence` array at each index to determine the health status of each cell.

---

## 📊 Health Status Criteria

The health status of each cell is determined using the following rules:

### ✅ **Healthy**
- Cell integrity > **75%** AND
- No pest presence (`false`)

### ⚠️ **At Risk**
- Cell integrity between **50% - 75%** (inclusive) OR
- Pest presence detected (`true`)

### ❌ **Unhealthy**
- Cell integrity < **50%**
- *Regardless of pest presence*

---

## 🔧 Function Specification

### Function Name
```javascript
checkPlantCellHealth(cellIntegrity, pestPresence)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `cellIntegrity` | `integer-array` | An array where each integer represents the integrity percentage of a plant cell |
| `pestPresence` | `boolean-array` | An array of the same length as `cellIntegrity`, where each boolean indicates pest presence (`true`) or absence (`false`) |

### Return Value

| Type | Description |
|------|-------------|
| `string-array` | An array of strings describing the health status of each cell ("Healthy", "At Risk", or "Unhealthy") |

---

## 💡 Example

```javascript
// Sample Input
const cellIntegrity = [80, 65, 45, 90, 55];
const pestPresence = [false, false, true, true, false];

// Expected Output
// ["Healthy", "At Risk", "Unhealthy", "At Risk", "At Risk"]
```

### Explanation:
- **Index 0**: 80% integrity, no pests → **Healthy**
- **Index 1**: 65% integrity, no pests → **At Risk** (50-75% range)
- **Index 2**: 45% integrity, pests present → **Unhealthy** (< 50%)
- **Index 3**: 90% integrity, pests present → **At Risk** (pest presence)
- **Index 4**: 55% integrity, no pests → **At Risk** (50-75% range)

---

## 📝 Implementation Notes

- Both arrays will always have the **same length**
- Integrity values are percentages (0-100)
- The function should return an array with the same length as the input arrays
- Each element in the output corresponds to the health status at the same index in the input arrays

---

## 🚀 Getting Started

Implement the `checkPlantCellHealth` function following the criteria above. Make sure to handle all edge cases and test your solution with various input combinations!

**Happy Coding!** 💻🌿
