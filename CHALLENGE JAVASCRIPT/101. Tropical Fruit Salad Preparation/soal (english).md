# 🥭 Tropical Fruit Salad Preparation Challenge

## 🏷️ Challenge Overview
**Difficulty Level:** `Easy`  
**Function Name:** `tropicalFruitSalad`

---

## 📖 Story Background
You are a **chef on a tropical island** known for reinventing traditional cuisine. Your mission is to prepare a unique tropical fruit salad using an array of fresh fruits. This challenge simulates the preparation process using basic array manipulation techniques including slicing, string operations, and array methods.

---

## 🎯 Challenge Requirements

### Function Signature
```javascript
function tropicalFruitSalad(fruits) {
    // Your implementation here
}
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `fruits` | `Array<string>` | An array of fruit names (strings) |

### Return Value
- **Type:** `Array<string>`
- **Description:** An array representing the prepared tropical fruit salad

---

## ⚙️ Processing Steps

The function must perform the following operations **in order**:

### 1. 🍊 Outer Layer Removal
- Remove the **first** and **last** fruits from the array
- This represents peeling off the outer layer of the fruit selection

### 2. 🍯 Sweetening Process (Even Indices)
- For every fruit at **even-indexed** positions `(0, 2, 4, ...)`
- Add `'y'` at the end of the fruit name
- This simulates the sweetening process

### 3. 🔪 Chopping Process (Odd Indices)
- For every fruit at **odd-indexed** positions `(1, 3, 5, ...)`
- Remove the **last character** from the fruit name
- This represents the chopping process

### 4. 🔄 Mixing the Salad
- **Reverse** the order of all remaining fruits
- This final step mixes the prepared salad

---

## ⚠️ Special Cases

> **Important Note:** If after removing the first and last fruits, the array becomes empty, return an **empty array** `[]`.

---

## 💡 Example Walkthrough

```javascript
// Input
const fruits = ["mango", "pineapple", "papaya", "coconut", "banana"];

// Step 1: Remove first and last
// ["pineapple", "papaya", "coconut"]

// Step 2 & 3: Process by index
// Index 0 (even): "pineapple" → "pineappley"
// Index 1 (odd): "papaya" → "papay" 
// Index 2 (even): "coconut" → "coconuty"
// Result: ["pineappley", "papay", "coconuty"]

// Step 4: Reverse the array
// Final result: ["coconuty", "papay", "pineappley"]
```

---

## 🎨 Implementation Tips

- Use array slicing methods for step 1
- Consider using a loop with index checking for steps 2 & 3
- Remember to handle the empty array edge case
- String concatenation and substring methods will be useful
- Don't forget to reverse the final result

---

## 🏁 Success Criteria

Your solution should:
- ✅ Handle all array sizes correctly
- ✅ Apply transformations in the correct order
- ✅ Return an empty array when appropriate
- ✅ Properly distinguish between even and odd indices
- ✅ Correctly reverse the final result

Happy coding! 🌴👨‍🍳
