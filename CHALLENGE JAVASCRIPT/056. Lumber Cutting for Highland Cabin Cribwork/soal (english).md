# 🏔️ Lumber Cutting for Highland Cabin Cribwork

## 🎯 Challenge Overview
**Difficulty Level:** `Easy`

Welcome to the Scottish Highlands! As a skilled carpenter working on a rustic cabin construction project, you'll be preparing lumber for the cabin's cribwork (framework). Your mission is to cut available lumber into standard lengths while minimizing waste.

---

## 📋 Task Description

Create a function named `cutLumberForCabin` that efficiently processes lumber pieces for construction.

### 🔧 Function Signature
```javascript
function cutLumberForCabin(availableLumber, standardLength)
```

### 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `availableLumber` | `Array<number>` | Array of numbers representing lumber piece lengths in feet |
| `standardLength` | `number` | The standard length needed for cribwork in feet |

### 📤 Return Value
- **Type:** `Array<number>`
- **Description:** Array containing the lengths of all processed lumber pieces

---

## 🛠️ Processing Rules

The lumber cutting follows these guidelines:

1. **Standard Cutting:** If a lumber piece is **longer than or equal to** the standard length, cut it into as many standard-length pieces as possible
2. **Preserve Short Pieces:** If a lumber piece is **shorter than** the standard length, keep it as is (no cutting needed)
3. **Minimize Waste:** Focus on getting the maximum number of standard pieces from each lumber

---

## 💡 Example Walkthrough

### Input:
- `availableLumber`: `[10, 15, 8]`
- `standardLength`: `5`

### Processing:
| Original Length | Action | Result Pieces |
|----------------|--------|---------------|
| 10 feet | Cut into standard pieces | `[5, 5]` |
| 15 feet | Cut into standard pieces | `[5, 5, 5]` |
| 8 feet | Keep as is (< standard) | `[8]` |

### Output:
```javascript
[5, 5, 5, 5, 5, 8]
```

---

## 🎯 Implementation Guidelines

- ✅ Use basic array methods and loops
- ✅ Focus on fundamental programming concepts
- ❌ Avoid advanced functions or complex methods
- ❌ No external libraries needed

---

## 🧠 Hints for Success

1. **Loop Through Each Piece:** Process each lumber piece individually
2. **Calculate Cuts:** Determine how many standard pieces can be cut from each lumber
3. **Handle Remainders:** Consider what to do with pieces shorter than standard length
4. **Build Result Array:** Collect all processed pieces into the final array

---

## 🏗️ Getting Started

Think about:
- How to iterate through the available lumber array
- How to determine the number of cuts possible for each piece
- How to add the resulting pieces to your output array
- When to preserve pieces that are too short to cut

Good luck with your Highland cabin project! 🏕️
