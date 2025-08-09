# 🐚 Shell Collector Simulator

## 📝 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that simulates collecting shells on a beach based on given commands. This challenge focuses on array manipulation and conditional logic.

---

## 🎯 Objective

Implement a function named `collectShells` that processes a series of commands to modify a collection of shells.

---

## 🔧 Function Specification

### Function Signature
```javascript
function collectShells(shells, commands)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `shells` | `Array<number>` | An array of positive integers representing the types of shells collected so far |
| `commands` | `Array<number>` | An array of integers representing the commands to perform |

### Return Value
- **Type:** `Array<number>`
- **Description:** The modified shells array after processing all commands

---

## ⚡ Command Logic

The function processes commands based on their sign:

### ✅ Positive Numbers
- **Action:** Collect a new shell
- **Behavior:** Add the number to the end of the `shells` array

### ❌ Negative Numbers  
- **Action:** Discard a shell
- **Behavior:** Remove the **last collected shell** of the corresponding type (if it exists)
- **Special Requirement:** Use the `continue` statement when removing shells

---

## 📋 Processing Rules

1. **Sequential Processing:** Process each command in the order they appear
2. **Type Matching:** For negative commands, match the absolute value with shell types
3. **Last Occurrence:** Always remove the last (rightmost) occurrence of the shell type
4. **Conditional Removal:** Only remove if the shell type exists in the collection
5. **Array Modification:** Modify the `shells` array directly based on commands

---

## 💡 Implementation Guidelines

### Key Requirements
- ✅ Handle positive commands by appending to array
- ✅ Handle negative commands by removing last occurrence
- ✅ Use `continue` statement for removal operations
- ✅ Maintain original order for remaining shells
- ✅ Return the final modified array

### Edge Cases to Consider
- Empty initial shells array
- Commands referencing non-existent shell types
- Multiple shells of the same type
- Zero commands
- Commands with value 0

---

## 📊 Example Scenarios

### Scenario 1: Basic Operations
```
Initial: [1, 2, 3]
Commands: [4, -2, 5]
Result: [1, 3, 4, 5]
```
*Explanation: Add 4, remove 2, add 5*

### Scenario 2: Multiple Same Types
```
Initial: [1, 2, 1, 3]
Commands: [-1]
Result: [1, 2, 3]
```
*Explanation: Remove the last occurrence of shell type 1*

### Scenario 3: Non-existent Shell
```
Initial: [1, 2, 3]
Commands: [-4, 5]
Result: [1, 2, 3, 5]
```
*Explanation: Shell type 4 doesn't exist, so add 5*

---

## 🏆 Success Criteria

Your solution should:
- ✅ Correctly handle both positive and negative commands
- ✅ Maintain proper array order after modifications
- ✅ Use the `continue` statement as specified
- ✅ Handle edge cases gracefully
- ✅ Return the correct final state of the shells array

---

## 🚀 Getting Started

1. Create the `collectShells` function with proper parameters
2. Implement a loop to process commands sequentially  
3. Add conditional logic for positive/negative commands
4. Implement shell removal logic for negative commands
5. Test with various scenarios to ensure correctness

Good luck with your shell collecting adventure! 🏖️
