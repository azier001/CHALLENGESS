# 💪 Gym Progress Tracker Challenge

## 🎯 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that helps track your workout progress by comparing exercise routines across different days. This challenge will help you practice array comparison and conditional logic in programming.

---

## 📋 Problem Description

Your task is to create a function named `gymProgressTracker` that analyzes workout consistency between two training sessions. The function will determine whether you stuck to the same routine or mixed things up!

### 🔍 How It Works

The function compares two workout sessions:
- **Same routine**: Identical exercises in the same order → Consistent training
- **Different routine**: Any variation in exercises or order → Mixed training approach

---

## ⚙️ Function Specifications

### Function Signature
```javascript
function gymProgressTracker(day1Exercises, day2Exercises)
```

### 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `day1Exercises` | `Array<string>` | List of exercises performed on Day 1 |
| `day2Exercises` | `Array<string>` | List of exercises performed on Day 2 |

### 📤 Return Values

| Condition | Return Value |
|-----------|-------------|
| Arrays are identical (same exercises, same order) | `"You did the same workout on both days!"` |
| Arrays have any differences | `"You mixed it up today!"` |

---

## 💡 Example Scenarios

### Scenario 1: Same Workout
```javascript
day1Exercises = ["push-ups", "squats", "planks"]
day2Exercises = ["push-ups", "squats", "planks"]
// Expected output: "You did the same workout on both days!"
```

### Scenario 2: Different Order
```javascript
day1Exercises = ["push-ups", "squats", "planks"]
day2Exercises = ["squats", "push-ups", "planks"]
// Expected output: "You mixed it up today!"
```

### Scenario 3: Different Exercises
```javascript
day1Exercises = ["push-ups", "squats"]
day2Exercises = ["push-ups", "burpees"]
// Expected output: "You mixed it up today!"
```

---

## 🎯 Key Requirements

- ✅ Compare two arrays of exercise strings
- ✅ Check for exact match (same exercises in same order)
- ✅ Return appropriate feedback message
- ✅ Handle arrays of any length
- ✅ Case-sensitive exercise name comparison

---

## 🧠 Hints & Tips

> **💡 Think About:**
> - How to compare arrays element by element
> - What constitutes "identical" arrays
> - Edge cases like empty arrays or different lengths

> **🔧 Useful Concepts:**
> - Array comparison techniques
> - Conditional statements
> - String comparison

---

## 🚀 Ready to Code?

Now it's time to implement your `gymProgressTracker` function! Remember to test it with different workout combinations to ensure it works correctly.

**Good luck with your coding workout! 💪**
