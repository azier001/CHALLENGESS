# 💝 Love Journey

## Challenge Overview

**Difficulty:** `Easy`

Create a function that calculates a love score by processing a memory book array with specific mathematical operations.

---

## 📋 Function Specification

### Function Name
```javascript
loveJourney(loveScore, memoryBook)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `loveScore` | Number | The initial love score value |
| `memoryBook` | Array<Number> | An array of numbers representing memories |

### Return Value

- **Type:** Number
- **Description:** The final calculated love score after processing all memories

---

## 🎯 Challenge Requirements

### Step-by-Step Process

#### **Step 1: Slice the Memory Book**
Extract a subset of the `memoryBook` array:
- **Start:** 2nd element (index `1`)
- **End:** 2nd to last element (index `length - 1`)

```javascript
// Example:
// memoryBook = [10, 20, 30, 40, 50]
// Sliced result = [20, 30, 40]
```

#### **Step 2: Process Each Memory**
Loop through the sliced array and update the `loveScore`:

- ✅ **If the element is EVEN:** Add it to `loveScore`
  ```
  loveScore += element
  ```

- ❌ **If the element is ODD:** Subtract it from `loveScore`
  ```
  loveScore -= element
  ```

#### **Step 3: Return the Result**
Return the final calculated `loveScore`

---

## 💡 Example Walkthrough

### Input
```javascript
loveScore = 100
memoryBook = [5, 10, 15, 20, 25, 30, 8]
```

### Process

1. **Slice the array:** `[10, 15, 20, 25, 30]`
   - From index 1 to index 5 (excluding last element)

2. **Loop through each element:**
   - `10` is even → `100 + 10 = 110`
   - `15` is odd → `110 - 15 = 95`
   - `20` is even → `95 + 20 = 115`
   - `25` is odd → `115 - 25 = 90`
   - `30` is even → `90 + 30 = 120`

3. **Return:** `120`

---

## 📝 Implementation Template

```javascript
function loveJourney(loveScore, memoryBook) {
  // Your code here
}
```

---

## ✅ Test Cases

```javascript
// Test Case 1
loveJourney(100, [5, 10, 15, 20, 25, 30, 8]);
// Expected output: 120

// Test Case 2
loveJourney(50, [1, 2, 3, 4, 5, 6, 7]);
// Expected output: 54

// Test Case 3
loveJourney(0, [10, 20, 30, 40, 50]);
// Expected output: 80
```

---

## 🎓 Key Concepts

This challenge helps you practice:

- 🔹 Array manipulation with `slice()`
- 🔹 Conditional logic (if/else statements)
- 🔹 Loop iteration
- 🔹 Even/odd number detection
- 🔹 Accumulator pattern

---

## 💪 Good Luck!

Remember to test your solution with different inputs to ensure it handles all cases correctly!
