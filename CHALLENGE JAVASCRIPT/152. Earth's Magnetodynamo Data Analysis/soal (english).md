# 🌍 Earth's Magnetodynamo Data Analysis Challenge

## Difficulty Level
**Easy** ⭐

---

## 📋 Challenge Overview

Assist a superaccomplished scientist in analyzing Earth's magnetodynamo data collected in their laboratory. Your task is to process input data arrays to reveal hidden geological patterns through systematic data manipulation and statistical analysis.

---

## 🎯 Objective

Create a function named **`analyzeMagnetodynamo`** that processes magnetic field measurements and calculates their average value after applying specific data transformations.

---

## 📊 Function Specification

### Function Signature
```javascript
analyzeMagnetodynamo(primaryData, secondaryData)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `primaryData` | Array of Numbers | Primary magnetic field measurements |
| `secondaryData` | Array of Numbers | Secondary magnetic field measurements |

### Return Value

- **Type:** Number
- **Description:** The calculated average (mean) of the processed data

---

## ⚙️ Processing Steps

The function must perform the following operations in sequence:

### 1. **Slice Primary Data**
   - Extract only the **first half** of elements from the `primaryData` array
   - Use array slicing techniques to maintain data integrity

### 2. **Slice Secondary Data**
   - Extract only the **last half** of elements from the `secondaryData` array
   - Ensure proper indexing for accurate results

### 3. **Concatenate Arrays**
   - Combine the sliced `primaryData` with the sliced `secondaryData`
   - Maintain the order: primary first, secondary last

### 4. **Calculate Average**
   - Compute the mean (average) of the resulting combined array
   - Return the final calculated value

---

## 💡 Example Usage

```javascript
const primary = [10, 20, 30, 40, 50, 60];
const secondary = [5, 15, 25, 35, 45, 55];

const result = analyzeMagnetodynamo(primary, secondary);
// Expected processing:
// - First half of primary: [10, 20, 30]
// - Last half of secondary: [35, 45, 55]
// - Combined: [10, 20, 30, 35, 45, 55]
// - Average: (10+20+30+35+45+55)/6 = 32.5
```

---

## 🔬 Scientific Context

The magnetodynamo is the mechanism by which Earth generates its magnetic field through the motion of molten iron in the outer core. This challenge simulates the process of:

- Filtering early-stage measurements (primary data)
- Selecting late-stage measurements (secondary data)
- Combining datasets for comprehensive analysis
- Deriving meaningful statistical insights

---

## ✅ Requirements Summary

- [ ] Function name: `analyzeMagnetodynamo`
- [ ] Accept two array parameters
- [ ] Slice first half of primary data
- [ ] Slice last half of secondary data
- [ ] Concatenate both sliced arrays
- [ ] Calculate and return the average
- [ ] Handle arrays of any length appropriately

---

**Good luck with your geological data analysis! 🧲🔍**
