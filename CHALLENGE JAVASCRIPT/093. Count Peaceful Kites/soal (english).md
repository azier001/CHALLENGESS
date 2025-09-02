# 🪁 Count Peaceful Kites

## 📋 Challenge Overview

**Difficulty:** `Easy`

Create a function that identifies and counts peaceful kites in a scene description based on their colors.

---

## 🎯 Problem Statement

Your task is to implement a function named `countPeacefulKites` that analyzes a scene description and counts how many kites are considered "peaceful" based on their color.

### What makes a kite peaceful?
A kite is considered **peaceful** if it's preceded by one of these specific colors:
- 🔴 Red
- 🔵 Blue  
- 🟢 Green
- 🟡 Yellow
- 🟣 Purple

---

## 📝 Function Specification

### Function Signature
```javascript
function countPeacefulKites(sceneDescription)
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `sceneDescription` | `string` | A description of the scene containing mentions of kites and their colors |

### Return Value
- **Type:** `number` (integer)
- **Description:** The total count of peaceful kites found in the scene

---

## 🔧 Implementation Requirements

Follow these steps to solve the challenge:

1. **🔤 Normalize Input**
   - Convert the input string to lowercase for case-insensitive matching

2. **🎨 Define Peaceful Colors**
   - Create an array containing the peaceful colors: `red`, `blue`, `green`, `yellow`, `purple`

3. **🔍 Search and Count**
   - Iterate through each peaceful color
   - Count occurrences of the pattern `"[color] kite"` in the string
   - Accumulate the total count

4. **📊 Return Result**
   - Return the final count of peaceful kites

---

## 💡 Example Usage

```javascript
// Example scene descriptions
const scene1 = "I saw a red kite flying high and a blue kite nearby";
const scene2 = "The black kite was aggressive, but the green kite was calm";
const scene3 = "Purple kite, yellow kite, and orange kite in the sky";

// Expected results
countPeacefulKites(scene1); // Returns: 2 (red kite + blue kite)
countPeacefulKites(scene2); // Returns: 1 (green kite only)
countPeacefulKites(scene3); // Returns: 2 (purple kite + yellow kite)
```

---

## 🎨 Pattern Matching

The function should match the exact pattern:
```
[peaceful_color] + space + "kite"
```

**Valid matches:**
- ✅ "red kite"
- ✅ "Blue Kite" (case-insensitive)
- ✅ "GREEN kite"

**Invalid matches:**
- ❌ "redkite" (no space)
- ❌ "red kites" (plural form)
- ❌ "dark red kite" (additional descriptors)

---

## 🏷️ Tags
`String Processing` • `Pattern Matching` • `Array Iteration` • `Case Insensitive` • `Easy`
