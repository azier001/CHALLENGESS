# 🫐 Juneberry Foraging Adventure
## 📋 Programming Problem Documentation

---

## 🌟 Overview

Imagine you are **Charlie**, a curious catechist foraging for Juneberries on a beautiful summer day. Charlie has come across a row of bushes and wants to count the Juneberries that can be picked, but has a limitation on how many berries can be carried.

### 🎯 **Main Mission**
Create a function `countJuneberries` that can count Juneberries in a row of bushes until reaching the end of the row or the maximum carrying capacity.

---

## 📝 Function Specification

### **Function Name:** `countJuneberries`

### **Input Parameters:**
| Parameter | Data Type | Description |
|-----------|-----------|-------------|
| `bushRow` | `string` | A string representing a row of bushes. Each character represents a part of the bush: `'J'` = Juneberry, other characters = leaves/branches |
| `maxBerries` | `number` | An integer representing the maximum number of Juneberries you want to collect |

### **Return Value:**
- **Type:** `string`
- **Format:** A message stating the number of Juneberries found and the foraging status

---

## 🔍 Foraging Rules

### ✅ **What Counts:**
- Only the character `'J'` (uppercase) is considered a Juneberry
- Case-sensitive: `'j'` (lowercase) does NOT count

### 🛑 **Stop Conditions:**
1. Reaching the `maxBerries` limit
2. Reaching the end of the `bushRow` string

### 📤 **Output Format:**
- **If maximum limit reached:** `"Found X Juneberries. Basket full!"`
- **If limit not reached:** `"Found X Juneberries. Keep foraging!"`

---

## 🔄 Algorithm Flow

```
1. 🏁 Initialize Juneberry counter = 0
2. 🔄 Loop through each character in bushRow
3. 🔍 If character is 'J':
   - Increment counter
4. ⚡ If counter = maxBerries OR reached end of string:
   - Break from loop
5. 📋 Return result string based on condition
```

---

## 🧪 Testing Scenarios

### **Scenario 1: Basket Full**
- **Input:** `bushRow = "JLJJBLJ"`, `maxBerries = 3`
- **Process:** Find 3 'J's before completion
- **Expected Output:** `"Found 3 Juneberries. Basket full!"`

### **Scenario 2: Need to Keep Foraging**
- **Input:** `bushRow = "LBLJBL"`, `maxBerries = 5`
- **Process:** Only find 1 'J' in the entire string
- **Expected Output:** `"Found 1 Juneberries. Keep foraging!"`

### **Scenario 3: No Juneberries Found**
- **Input:** `bushRow = "LBLBL"`, `maxBerries = 3`
- **Process:** No 'J' found at all
- **Expected Output:** `"Found 0 Juneberries. Keep foraging!"`

### **Scenario 4: Empty Bush Row**
- **Input:** `bushRow = ""`, `maxBerries = 2`
- **Process:** Empty string, no characters to check
- **Expected Output:** `"Found 0 Juneberries. Keep foraging!"`

### **Scenario 5: Mixed Case Characters**
- **Input:** `bushRow = "JjJjBL"`, `maxBerries = 5`
- **Process:** Only uppercase 'J' counts (2 berries)
- **Expected Output:** `"Found 2 Juneberries. Keep foraging!"`

---

## ⚠️ Important Notes

- **Case Sensitivity:** Only `'J'` (uppercase) counts as Juneberries
- **Efficiency:** Loop stops immediately after reaching `maxBerries`
- **Edge Cases:** Consider empty strings, maxBerries = 0, etc.
- **String Indexing:** Be careful with array bounds to avoid errors

---

## 🎨 Implementation Tips

💡 **Use a loop with break condition**  
💡 **Watch out for array index bounds**  
💡 **Test with various input combinations**  
💡 **Ensure output string format matches specification exactly**  
💡 **Consider early termination for efficiency**  
💡 **Handle edge cases gracefully**

---

## 🔧 Technical Considerations

### **Performance:**
- Time Complexity: O(n) where n is the length of bushRow (worst case)
- Space Complexity: O(1) - only using a counter variable

### **Validation:**
- Input validation may be needed for edge cases
- Consider handling non-string or non-number inputs

### **Testing Strategy:**
- Unit tests for normal cases
- Edge case testing (empty strings, zero limits)
- Boundary testing (exact limit matches)
- Invalid input handling

---

## 📚 Learning Objectives

This problem helps practice:
- **String iteration and character checking**
- **Conditional logic and loop control**
- **Early termination optimization**
- **String formatting and output generation**
- **Edge case handling**

---

> **🌟 Happy Coding! May Charlie successfully collect those delicious Juneberries! 🫐**
