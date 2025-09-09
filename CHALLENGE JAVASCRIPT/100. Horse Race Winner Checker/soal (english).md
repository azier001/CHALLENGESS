# 🏇 Horse Race Winner Checker

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function named `horseRaceWinnerChecker` that determines the winner of a horse race based on current positions and spectator flags.

---

## 🎯 Objective

Your task is to calculate points for each horse and identify the race winner. The scoring system combines positional advantages with spectator support through flag-waving.

---

## 📊 Scoring System

### Position Points
| Position | Points Awarded |
|----------|----------------|
| 🥇 1st Place | **3 points** |
| 🥈 2nd Place | **2 points** |
| 🥉 3rd Place | **1 point** |
| 4th+ Place | **0 points** |

### Flag Bonus Points
- **+1 point** for each spectator flag that matches the horse's color
- Color matching is based on the **first word** of the horse's name
- Case-insensitive matching

### Tie-Breaking Rule
> 🏁 In case of a tie, the horse that appears **earlier** in the original `horses` array wins.

---

## 🔧 Function Specification

### Function Signature
```javascript
function horseRaceWinnerChecker(horses, flags)
```

### Parameters

#### `horses` (Array of Strings)
- **Description:** Horses listed in order of current race position
- **Format:** Each horse name starts with a color identifier
- **Example:** `["Red Stallion", "Blue Thunder", "Green Lightning"]`

#### `flags` (Array of Strings)  
- **Description:** Flags being waved by spectators
- **Format:** Lowercase color names
- **Example:** `["red", "green", "blue", "red"]`

### Return Value
- **Type:** String
- **Description:** The name of the winning horse

---

## 📏 Constraints

| Parameter | Minimum | Maximum | Valid Values |
|-----------|---------|---------|--------------|
| `horses` array | 1 horse | 5 horses | Names starting with colors |
| `flags` array | 1 flag | 100 flags | Color strings only |

### Supported Colors
- 🔴 `red`
- 🔵 `blue` 
- 🟢 `green`
- 🟡 `yellow`
- ⚪ `white`

---

## 💡 Example Scenarios

### Scenario 1: Basic Race
```javascript
horses = ["Red Stallion", "Blue Thunder", "Green Lightning"]
flags = ["red", "red", "blue"]

// Scoring:
// Red Stallion: 3 (1st place) + 2 (red flags) = 5 points ← Winner
// Blue Thunder: 2 (2nd place) + 1 (blue flag) = 3 points
// Green Lightning: 1 (3rd place) + 0 (no green flags) = 1 point
```

### Scenario 2: Tie-Breaking
```javascript
horses = ["Yellow Flash", "White Storm"]
flags = ["white", "white", "white"]

// Scoring:
// Yellow Flash: 3 (1st place) + 0 (no yellow flags) = 3 points ← Winner (tie-breaker)
// White Storm: 2 (2nd place) + 3 (white flags) = 5 points
```

---

## ✅ Success Criteria

Your function should:
- ✓ Correctly calculate position points (3-2-1-0)
- ✓ Accurately count matching flag bonuses
- ✓ Handle tie-breaking by original array position
- ✓ Return the exact horse name as provided
- ✓ Work with all constraint combinations (1-5 horses, 1-100 flags)

---

## 🚀 Getting Started

Ready to implement your solution? Remember to:
1. Parse horse colors from the first word of each name
2. Calculate both positional and flag bonus points
3. Handle tie-breaking logic properly
4. Test with edge cases and different scenarios

Good luck! 🍀
