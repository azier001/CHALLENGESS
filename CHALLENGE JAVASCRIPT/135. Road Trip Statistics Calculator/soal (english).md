# 🚗 Road Trip Statistics Calculator

> **Difficulty:** `Easy` | **Topic:** Array Manipulation & Statistics

---

## 📋 Challenge Description

Create a function named `calculateTripStats` that analyzes a cross-country road trip through America's diverse landscapes. Your function will calculate various statistics based on daily mileage data.

---

## 🎯 Objective

Analyze an array of daily mileage and compute comprehensive trip statistics including totals, averages, and extreme values.

---

## 📊 Required Statistics

Your function should calculate and return the following information:

- **Total Miles** - Sum of all miles driven during the entire trip
- **Average Miles** - Average miles driven per day
- **Maximum Day** - The day when you drove the most miles *(0-based index)*
- **Minimum Day** - The day when you drove the least miles *(0-based index)*
- **Trip Duration** - The total number of days the trip lasted

---

## 🔧 Function Specification

### Function Name
```javascript
calculateTripStats
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `dailyMiles` | `array` | An array of numbers representing the miles driven each day of the trip |

### Return Value

**Type:** `Object`

The function returns an object containing all the calculated statistics.

---

## ⚠️ Important Constraints

> **Note:** Do not use built-in methods like `Math.max()` or `Math.min()`. 
> 
> Instead, use **basic array iteration** and **comparison operations** to find the maximum and minimum values.

---

## 💡 Implementation Tips

- Use loops to iterate through the array
- Keep track of running totals for sum calculation
- Compare values manually to find max/min
- Store indices while finding extreme values
- Calculate average after determining the total

---

## 🚀 Getting Started

Begin by defining your function structure:

```javascript
function calculateTripStats(dailyMiles) {
  // Your implementation here
}
```

Good luck with your coding journey! 🛣️
