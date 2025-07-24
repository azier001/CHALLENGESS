# 🎓 Academic Debate Winner Challenge

## 📊 Challenge Information
- **Difficulty Level:** `Easy`
- **Challenge Type:** Function Implementation
- **Topic:** String Manipulation & Array Processing

---

## 🎯 Challenge Overview

Create a function that simulates an intense academic debate between two scholars and determines the winner based on the strength of their arguments. This challenge tests your ability to compare arrays, process strings, and implement scoring logic.

## 📝 Function Specification

### Function Name
```javascript
debateWinner(scholar1Arguments, scholar2Arguments)
```

### 🔍 Problem Description

The function simulates a **heated academic debate** between two scholars where the winner is determined by comparing the strength of their arguments. The strength of each argument is measured by its **string length**.

### ⚖️ Scoring Rules

The debate follows these specific rules for determining points:

1. **🏆 Head-to-Head Comparison**
   - If Scholar 1's argument is **longer** than Scholar 2's corresponding argument → Scholar 1 gets **1 point**
   - If Scholar 2's argument is **longer** than Scholar 1's corresponding argument → Scholar 2 gets **1 point**
   - If both arguments have the **same length** → **No points** awarded

2. **📊 Extra Arguments Bonus**
   - If a scholar has **more arguments** than their opponent, they automatically win points for each extra argument

3. **🏅 Victory Conditions**
   - The scholar with the **highest total score** wins the debate
   - If both scholars have the **same score** → It's a tie

---

## 🔧 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `scholar1Arguments` | `Array<String>` | An array of strings representing the first scholar's arguments |
| `scholar2Arguments` | `Array<String>` | An array of strings representing the second scholar's arguments |

---

## 📤 Return Value

The function returns a **string** indicating the debate outcome:

| Return Value | Condition |
|--------------|-----------|
| `"Scholar 1 wins!"` | When Scholar 1 has more points |
| `"Scholar 2 wins!"` | When Scholar 2 has more points |
| `"It's a tie!"` | When both scholars have equal points |

---

## 💡 Example Scenarios

### Scenario 1: Clear Winner
```javascript
scholar1Arguments = ["Long argument here", "Short"]
scholar2Arguments = ["Brief", "Medium length argument"]
// Scholar 1: 18 vs 5 (1 point), 5 vs 20 (0 points) = 1 point
// Scholar 2: 5 vs 18 (0 points), 20 vs 5 (1 point) = 1 point
// Result: "It's a tie!"
```

### Scenario 2: Extra Arguments
```javascript
scholar1Arguments = ["Argument", "Another", "Extra one"]
scholar2Arguments = ["Argument", "Another"]
// Equal on first two, Scholar 1 gets 1 point for extra argument
// Result: "Scholar 1 wins!"
```

---

## 🎯 Key Implementation Points

- Compare argument lengths character by character
- Handle arrays of different lengths appropriately  
- Implement proper scoring logic for all scenarios
- Return the correct winner string format

---

## 🚀 Ready to Code?

Time to implement your `debateWinner` function and settle this academic dispute! Good luck! 🍀
