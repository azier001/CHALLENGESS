# 🎯 Exam Panic: Matrix Manipulation

## 📊 Challenge Overview
**Difficulty:** `Easy`  
**Topic:** Matrix Operations & Array Manipulation

---

## 🎭 The Scenario

Picture this: You're a nervous student sitting in your final licensing exam at the university. Your palms are sweaty, your heart is racing, and you're staring at a complex math problem involving matrices. In your anxious state, you need to perform a series of operations to solve the problem and pass your exam!

## 🎯 Your Mission

Create a function named **`examPanic`** that takes a matrix as its parameter and performs the following operations:

### 📝 Required Operations

1. **📊 Sum Calculation**
   - Calculate the sum of all elements in the original matrix

2. **🔄 Row Reversal**
   - Reverse the order of elements in each row of the matrix

3. **🔢 Diagonal Product**
   - Calculate the product of diagonal elements (from top-left to bottom-right) in the reversed matrix

---

## 📋 Function Specification

### Function Signature
```javascript
function examPanic(matrix) {
    // Your implementation here
}
```

### Parameters
- **`matrix`** *(integer-2d-array)*: A 2D array of integers representing the math problem on your exam paper. Each sub-array represents a row in the matrix.

### Return Value
The function returns an **array** containing three elements:
```javascript
[sum, reversedMatrix, diagonalProduct]
```

Where:
- **`sum`** *(integer)*: The sum of all elements in the original matrix
- **`reversedMatrix`** *(integer-2d-array)*: The matrix after reversing each row
- **`diagonalProduct`** *(integer)*: The product of diagonal elements in the reversed matrix

---

## 💡 Example

### Input Matrix:
```
[
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]
```

### Step-by-Step Process:

1. **Sum of all elements:** `1+2+3+4+5+6+7+8+9 = 45`

2. **Reversed matrix (each row reversed):**
   ```
   [
     [3, 2, 1],
     [6, 5, 4],
     [9, 8, 7]
   ]
   ```

3. **Diagonal product:** `3 × 5 × 7 = 105`

### Expected Output:
```javascript
[45, [[3, 2, 1], [6, 5, 4], [9, 8, 7]], 105]
```

---

## 🔍 Key Points to Remember

- ⚠️ Work with the **original matrix** for sum calculation
- 🔄 Apply row reversal to create a **new matrix**
- 🎯 Calculate diagonal product from the **reversed matrix**
- 📦 Return all three results in a single array

---

## 🚀 Ready to Tackle the Challenge?

Take a deep breath, channel your inner mathematician, and show that exam who's boss! Remember, even in a state of panic, systematic thinking will guide you to the solution.

*Good luck, future graduate!* 🎓
