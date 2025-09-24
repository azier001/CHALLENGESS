# 🔨 Blacksmith Workshop Challenge

## 📋 Problem Overview

**Function Name:** `sortMetalPieces`  
**Difficulty Level:** `Easy`  
**Category:** Array Sorting & String Manipulation

---

## 🎯 Challenge Description

Create a function that organizes metal pieces in a blacksmith's workshop based on their weight, simulating the use of a pulley system for lifting. The function will sort the pieces by weight and return a formatted string describing the optimal lifting order.

> **Scenario:** A blacksmith needs to lift various metal pieces using a pulley system. To work efficiently and safely, lighter pieces should be lifted first, gradually progressing to heavier ones.

---

## 🔧 Function Requirements

### Function Signature
```javascript
function sortMetalPieces(pieces)
```

### Parameters
- **`pieces`** *(string array)*: An array of strings representing metal pieces
  - Format: `"name-weight"`
  - Example: `["anvil-50", "hammer-5", "tongs-2"]`

### Return Value
- **Type:** `string`
- **Format:** `"Lift order: 1. [piece name], 2. [piece name], ..., N. [piece name]"`

---

## ⚙️ Implementation Steps

The function should perform the following operations:

1. **Parse Weight Data**
   - Extract weight from each string in the input array
   - Handle the "name-weight" format correctly

2. **Sort by Weight**
   - Arrange metal pieces in ascending order by weight
   - Lightest pieces should come first

3. **Format Output**
   - Create a descriptive string showing the lifting order
   - Display only the metal piece names (without weights)
   - Use numbered list format for clarity

---

## 📐 Constraints & Rules

| Constraint | Description |
|------------|-------------|
| **Minimum Input** | Array contains at least one metal piece |
| **String Format** | Each string follows "name-weight" pattern exactly |
| **Weight Values** | Always positive integers |
| **Naming Convention** | Metal piece names will not contain hyphens |
| **Data Integrity** | All input will be in correct format |

---

## 💡 Example Usage

### Input
```javascript
["anvil-50", "hammer-5", "tongs-2", "horseshoe-3"]
```

### Expected Output
```
"Lift order: 1. tongs, 2. horseshoe, 3. hammer, 4. anvil"
```

### Step-by-step Process
1. **Parse:** Extract weights → `{tongs: 2, horseshoe: 3, hammer: 5, anvil: 50}`
2. **Sort:** Arrange by weight → `[tongs-2, horseshoe-3, hammer-5, anvil-50]`
3. **Format:** Create numbered list showing only the metal piece names

---

## 🎨 Output Format Details

The returned string must follow this exact pattern:

```
Lift order: 1. [piece name], 2. [piece name], ..., N. [piece name]
```

**Key Points:**
- Starts with "Lift order: "
- Each item numbered sequentially
- Shows only metal piece names (weights are used for sorting but not displayed)
- Comma-separated list
- No trailing comma

---

## 🔍 Edge Cases to Consider

- **Single Item:** Handle arrays with only one metal piece
- **Equal Weights:** Maintain consistent ordering for pieces with same weight
- **Various Name Lengths:** Support both short and long metal piece names
- **Large Weight Values:** Handle multi-digit weight numbers correctly

---

## 🏆 Success Criteria

✅ Correctly parses weight from each string  
✅ Sorts pieces in ascending order by weight  
✅ Returns properly formatted string with piece names only  
✅ Handles all constraints and edge cases  
✅ Uses weights for sorting but displays only names in output
