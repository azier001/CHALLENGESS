# 🌺 Orchid Picket Shuffle

> **Difficulty Level:** `Easy` 🟢

## 📋 Challenge Overview

Help a botanist in a greenhouse properly label orchid pickets! Each picket is marked with a number, but to ensure the orchids receive adequate sunlight, the digits need special processing.

## 🎯 Objective

Create a function named `orchidPicketShuffle` that transforms picket numbers through a specific digit manipulation process.

## 📥 Function Signature

```javascript
function orchidPicketShuffle(picketNumber)
```

### Parameters
- **`picketNumber`** *(number)*: The original number marked on the orchid picket

### Returns
- **`number`**: The transformed picket number after processing

## ⚙️ Algorithm Steps

The function must perform the following operations **in order**:

1. **🔄 Convert to String**
   - Transform the `picketNumber` to a string to access individual digits

2. **↩️ Reverse Digits**
   - Reverse the order of digits in the string

3. **➕ Increment Each Digit**
   - Add 1 to each digit
   - **Special Rule:** `9` becomes `0` after increment

4. **🔗 Combine Results**
   - Join the modified digits back into a string

5. **🔢 Convert to Integer**
   - Transform the final string back to a number

## 💡 Examples

### Example 1
```
Input:  1234
Step 1: "1234"        (convert to string)
Step 2: "4321"        (reverse digits)
Step 3: "5432"        (increment each: 4→5, 3→4, 2→3, 1→2)
Output: 5432
```

### Example 2
```
Input:  9876
Step 1: "9876"        (convert to string)
Step 2: "6789"        (reverse digits)
Step 3: "7890"        (increment each: 6→7, 7→8, 8→9, 9→0)
Output: 7890
```

## 🔍 Key Points to Remember

- ⚠️ **Important:** Digit `9` wraps around to `0` when incremented
- 📊 The transformation affects both **order** and **value** of digits
- 🎪 Operations must be performed in the **exact sequence** specified

## 🧪 Test Cases

| Input | Reversed | After Increment | Output |
|-------|----------|-----------------|--------|
| `1234` | `"4321"` | `"5432"` | `5432` |
| `9876` | `"6789"` | `"7890"` | `7890` |
| `505` | `"505"` | `"616"` | `616` |
| `9999` | `"9999"` | `"0000"` | `0` |

---

*Happy coding! 🚀 Transform those orchid pickets and help the botanist create the perfect greenhouse environment!*
