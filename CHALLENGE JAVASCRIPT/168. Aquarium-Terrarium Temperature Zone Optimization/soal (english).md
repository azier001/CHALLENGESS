# 🌡️ Aquarium-Terrarium Temperature Zone Optimization

## 📊 Challenge Level
**Medium** ⭐⭐

---

## 🎯 Problem Statement

You're setting up a mixed aquarium-terrarium display with multiple habitat sections, each monitored by temperature sensors. Your task is to process sensor data to ensure optimal environmental balance across all habitats.

Write a function **`calculateOptimalZones`** that analyzes temperature readings from various habitat sections and returns the mathematical mean of each reversed temperature array.

---

## 🔧 Function Specification

### Function Name
```javascript
calculateOptimalZones(temperatureReadings)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `temperatureReadings` | `Array<Array<number>>` | 2D array where each sub-array contains temperature readings from a habitat section |

**Example Input:**
```javascript
[
  [20.5, 21.0, 22.3, 23.1],
  [25.0, 26.5, 27.2],
  [19.8, 20.1, 21.5, 22.0, 22.8]
]
```

### Returns

**Type:** `Array<number>`

An array of mean temperatures for each section after reversal, rounded to 2 decimal places.

**Example Output:**
```javascript
[23.45, 26.78, 21.33]
```

---

## 📋 Processing Logic

The function must perform the following steps:

1. **🔄 Reverse Each Temperature Array**
   - Use an optimized reversal algorithm
   - Process each habitat section's readings independently

2. **🧮 Calculate Mathematical Mean**
   - Compute the average of each reversed array
   - Formula: `mean = sum of all values / count of values`

3. **✨ Format Results**
   - Round each mean to **2 decimal places**
   - Return as an array of numbers

---

## 💡 Example Walkthrough

### Input:
```javascript
temperatureReadings = [
  [20.0, 21.0, 22.0],
  [25.0, 26.0, 27.0, 28.0]
]
```

### Step-by-Step Processing:

#### Section 1: `[20.0, 21.0, 22.0]`
- **Reversed:** `[22.0, 21.0, 20.0]`
- **Mean:** `(22.0 + 21.0 + 20.0) / 3 = 21.00`

#### Section 2: `[25.0, 26.0, 27.0, 28.0]`
- **Reversed:** `[28.0, 27.0, 26.0, 25.0]`
- **Mean:** `(28.0 + 27.0 + 26.0 + 25.0) / 4 = 26.50`

### Output:
```javascript
[21.00, 26.50]
```

---

## ✅ Requirements Checklist

- [ ] Reverse each temperature array efficiently
- [ ] Calculate accurate mathematical mean for each section
- [ ] Round results to exactly 2 decimal places
- [ ] Return results as an array of numbers
- [ ] Handle empty arrays appropriately (if applicable)

---

## 🚀 Getting Started

```javascript
function calculateOptimalZones(temperatureReadings) {
  // Your implementation here
}

// Test your function
const readings = [
  [20.5, 21.0, 22.3, 23.1],
  [25.0, 26.5, 27.2],
  [19.8, 20.1, 21.5, 22.0, 22.8]
];

console.log(calculateOptimalZones(readings));
// Expected output: [23.45, 26.78, 21.33]
```

---

## 🏆 Success Criteria

Your solution should:
- ✨ Produce correct mean values for all test cases
- 🎯 Handle arrays of varying lengths
- 💯 Maintain precision with 2 decimal places
- ⚡ Use efficient array manipulation techniques

---

*Good luck with your habitat optimization! 🐠🌿*
