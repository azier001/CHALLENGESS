# 🎵 Community Park Music Pavilion Planner

> **Difficulty Level:** Medium

---

## 📋 Challenge Overview

Create a function `planParkDay` that manages the community park's music pavilion operations. This function processes performance schedules, calculates space requirements based on audience sizes, and identifies the next pending maintenance task.

---

## 🎯 Function Signature

```javascript
function planParkDay(schedules, inventory, audienceCounts, tasks)
```

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `schedules` | `array` | Performance entries in format `"BandName@Time"` |
| `inventory` | `object` | Instrument names mapped to available counts |
| `audienceCounts` | `array` | Expected audience size for each scheduled performance |
| `tasks` | `array` | Maintenance tasks in format `"task-name:status"` |

---

## 🔧 Logic Requirements

### 1. **Schedule Summary Generation**
Concatenate all schedule entries with their corresponding audience counts to create a comprehensive summary string.

**Format:** `"BandName@Time(audienceCount)"`

### 2. **Space Calculation**
Calculate the total space needed by:
- Applying the formula: `Math.floor(count * 1.5)` to each audience count
- Summing all the calculated results

### 3. **Maintenance Task Identification**
Loop through maintenance tasks to find the first one with `"pending"` status:
- Use **break/continue** statements for efficient searching
- Return only the task name (without status)

---

## 📤 Return Value

The function returns an **object** with the following structure:

```javascript
{
  "summary": "BandA@10:00(50)BandB@14:00(75)",
  "spaceNeeded": 187,
  "nextMaintenance": "mow-grass"
}
```

### Return Object Properties

- **`summary`** _(string)_: Concatenated performance schedule with audience counts
- **`spaceNeeded`** _(number)_: Total calculated space required for all performances
- **`nextMaintenance`** _(string)_: Name of the first pending maintenance task

---

## 💡 Example

### Input:
```javascript
const schedules = ["RockBand@10:00", "JazzTrio@14:00"];
const inventory = { guitar: 5, drums: 2, keyboard: 3 };
const audienceCounts = [50, 75];
const tasks = ["clean-stage:completed", "mow-grass:pending", "repair-lights:pending"];
```

### Output:
```javascript
{
  "summary": "RockBand@10:00(50)JazzTrio@14:00(75)",
  "spaceNeeded": 187,
  "nextMaintenance": "mow-grass"
}
```

### Calculation Breakdown:
- **Space for 50 audience:** `Math.floor(50 * 1.5) = 75`
- **Space for 75 audience:** `Math.floor(75 * 1.5) = 112`
- **Total space needed:** `75 + 112 = 187`

---

## ✅ Key Points to Remember

- Ensure the summary string has **no spaces or separators** between schedule entries
- The space calculation uses `Math.floor()` to round down to the nearest integer
- Only return the **first pending task** found in the tasks array
- The `inventory` parameter is provided but may not be used in the core logic

---

## 🚀 Implementation Tips

1. Use array methods like `map()` and `reduce()` for efficient data processing
2. Implement proper loop control with `break` when finding the first pending task
3. Handle edge cases (empty arrays, no pending tasks, etc.)
4. Ensure data type consistency in the return object

---

**Good luck with your implementation! 🎪**
