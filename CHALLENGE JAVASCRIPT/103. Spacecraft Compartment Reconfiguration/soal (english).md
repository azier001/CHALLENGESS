# 🚀 Spacecraft Compartment Reconfiguration

## Challenge Overview

**Difficulty Level:** `Easy` ⭐

Create a function that simulates the reconfiguration of a vintage spacecraft's compartments by adding custom spacers between them to enhance performance and compatibility.

---

## 📋 Problem Description

Your mission is to develop a function named `reconfigureSpacecraft` that takes spacecraft compartment data and inserts spacers between compartments for optimal configuration.

### Function Signature
```javascript
function reconfigureSpacecraft(compartmentSizes, spacerSize)
```

---

## 🎯 Objective

Transform an array of compartment sizes by inserting spacers between each compartment, creating a reconfigured spacecraft layout that improves performance and compatibility with new custom spacers.

---

## 📝 Algorithm Steps

Follow these precise steps to reconfigure the spacecraft:

1. **Initialize** - Create a new empty array called `reconfiguredSizes` to store the results
2. **Iterate** - Loop through each compartment size in the input array
3. **Process Each Compartment**:
   - ✅ Append the current compartment size to `reconfiguredSizes`
   - ✅ If it's **not** the last compartment, append the `spacerSize` as well
4. **Return** - Output the `reconfiguredSizes` array with spacers inserted

---

## 📊 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `compartmentSizes` | `Array<number>` | An array of integers representing the sizes of spacecraft compartments |
| `spacerSize` | `number` | An integer representing the size of spacer to insert between compartments |

---

## 📤 Return Value

**Type:** `Array<number>`

**Description:** An array of integers representing the reconfigured compartment sizes with spacers added between each original compartment.

---

## 💡 Example

### Input:
```javascript
compartmentSizes = [10, 20, 15, 30]
spacerSize = 5
```

### Expected Output:
```javascript
[10, 5, 20, 5, 15, 5, 30]
```

### Visual Representation:
```
Original:  [10] [20] [15] [30]
                ↓
Reconfigured: [10] [5] [20] [5] [15] [5] [30]
```

---

## 🎨 Implementation Tips

- Use array methods like `push()` or spread operator for adding elements
- Consider using a loop with index tracking to identify the last element
- Remember: no spacer should be added after the final compartment

---

## 🧪 Test Cases

Consider testing your function with these scenarios:

- **Single compartment:** `[100]` → `[100]`
- **Two compartments:** `[10, 20]` → `[10, 5, 20]` (assuming spacerSize = 5)
- **Empty array:** `[]` → `[]`
- **Large spacers:** Test with spacer sizes larger than compartment sizes

---

*Good luck with your spacecraft reconfiguration mission! 🚀✨*
