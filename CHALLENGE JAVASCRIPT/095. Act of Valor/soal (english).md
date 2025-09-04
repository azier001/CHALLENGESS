# 🏆 Act of Valor

## 📋 Challenge Overview

**Difficulty Level:** `Easy`  
**Topic:** Control Flow - Switch Statements  
**Language:** JavaScript

---

## 🎯 Objective

Create a function that determines whether a given action qualifies as an "act of valor" using a switch statement to evaluate different scenarios.

## 📝 Problem Description

You need to implement a function named `actOfValor` that:

- **Accepts:** A `string` parameter representing an action
- **Uses:** A `switch` statement for decision making
- **Returns:** A specific message based on the action type

## ✅ Requirements

### Function Specification
```javascript
function actOfValor(action) {
    // Your implementation here
}
```

### Decision Logic

The function should evaluate actions using a `switch` statement:

#### Acts of Valor ⚔️
Return: `"This is an act of valor!"`

- `"save a life"`
- `"help the elderly"` 
- `"defend the weak"`

#### Other Actions 🚫
Return: `"This action is not considered an act of valor."`

- Any action not listed above

---

## 💡 Implementation Hints

1. Use a `switch` statement as the primary control structure
2. Consider using `case` statements for each valorous action
3. Include a `default` case for non-valorous actions
4. Remember to use `break` statements to prevent fall-through

## 🔍 Example Usage

```javascript
// Expected outputs
actOfValor("save a life");     // "This is an act of valor!"
actOfValor("help the elderly"); // "This is an act of valor!"
actOfValor("defend the weak");  // "This is an act of valor!"
actOfValor("eat pizza");       // "This action is not considered an act of valor."
```

---

## 🎨 Code Structure Template

```javascript
function actOfValor(action) {
    switch (action) {
        // Add your cases here
        
        default:
            // Default case logic
    }
}
```

## 🏅 Success Criteria

- ✅ Function uses a `switch` statement
- ✅ Correctly identifies all three acts of valor
- ✅ Returns appropriate messages for both scenarios
- ✅ Handles any input string properly
- ✅ Code is clean and readable

---

**Good luck with your implementation! 🚀**
