# 🥾 Hiker's Performance Score Calculator

> **Challenge Level:** `Easy` 🟢

## 📋 Overview

Create a function named `calculateHikeScore` that simulates a hike through rolling hills and calculates a hiker's performance score based on various criteria including hills climbed, distance covered, and response to safety protocols.

## 🎯 Function Requirements

### Function Signature
```javascript
function calculateHikeScore(hills, distance, whistleResponse)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `hills` | `number` | The number of hills climbed during the hike (non-negative integer) |
| `distance` | `number` | The total distance hiked in kilometers (non-negative number) |
| `whistleResponse` | `boolean` | Whether the hiker responded correctly to the forest ranger's whistle |

### Return Value
- **Type:** `integer`
- **Description:** The final calculated performance score

## 🏆 Scoring System

The hiker's performance is evaluated using the following comprehensive scoring system:

### ✅ Point Rewards

- **🏔️ Base Score**
  - **+10 points** for each hill climbed
  
- **🚶 Distance Bonus**
  - **+5 points** for every full kilometer hiked
  
- **📯 Ranger's Whistle Bonus**
  - **+50 points** if the hiker responded correctly to the whistle (`true`)
  
- **💪 Endurance Bonus**
  - **+100 points** if more than 10 hills were climbed

### ⚠️ Penalties

- **🚩 Short Hike Penalty**
  - **-20 points** if total distance is less than 5 km

## 📝 Example Scenarios

### Scenario 1: Excellent Performance
- Hills: `15`
- Distance: `12.5 km`
- Whistle Response: `true`
- **Expected calculation:** Base (150) + Distance (60) + Whistle (50) + Endurance (100) = **360 points**

### Scenario 2: Average Performance
- Hills: `8`
- Distance: `6.2 km`
- Whistle Response: `false`
- **Expected calculation:** Base (80) + Distance (30) = **110 points**

### Scenario 3: Short Hike with Penalty
- Hills: `3`
- Distance: `3.8 km`
- Whistle Response: `true`
- **Expected calculation:** Base (30) + Distance (15) + Whistle (50) - Short Hike Penalty (20) = **75 points**

## 🎨 Implementation Notes

- Use `Math.floor()` for distance calculations to count only full kilometers
- Ensure proper handling of boolean values for whistle response
- Return the final score as an integer
- Consider edge cases with zero values

## 🚀 Getting Started

1. Define the function with the required parameters
2. Calculate the base score from hills climbed
3. Add distance bonus for full kilometers
4. Check and apply whistle response bonus
5. Apply endurance bonus if applicable
6. Apply short hike penalty if applicable
7. Return the final calculated score

---

**Happy coding!** 🎉
