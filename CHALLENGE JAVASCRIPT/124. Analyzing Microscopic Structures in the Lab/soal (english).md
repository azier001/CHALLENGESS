# 🔬 Analyzing Microscopic Structures in the Lab

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

You are a scientist in a laboratory examining microscopic structures. Your task is to develop a program that helps in analyzing the lab data by searching through structures and providing detailed analysis reports.

---

## 🎯 Objective

Create a function named **`analyzeMicrostructures`** that searches through an array of microscopic structures to find a specific target structure and returns a formatted analysis report.

---

## 📥 Function Parameters

The function accepts two parameters:

| Parameter | Type | Description |
|-----------|------|-------------|
| `structures` | `array` | An array of strings where each string represents a microscopic structure |
| `target` | `string` | The specific structure you are searching for within the array |

---

## 📤 Expected Output

The function should return a **string** with one of the following formats:

### ✅ When Target is Found

```
Structure '[target]' found at position [position]. Total structures examined: [total].
```

### ❌ When Target is Not Found

```
Structure '[target]' not found. Total structures examined: [total].
```

---

## 📌 Important Notes

> **Position Indexing:** The position should be reported as `index + 1` to make it more user-friendly.
> 
> - The first element is at **position 1** (not 0)
> - The second element is at **position 2** (not 1)
> - And so on...

---

## 💡 Example Usage

### Example 1: Target Found

**Input:**
```javascript
structures = ["cell", "bacteria", "virus", "protein"]
target = "virus"
```

**Output:**
```
Structure 'virus' found at position 3. Total structures examined: 4.
```

### Example 2: Target Not Found

**Input:**
```javascript
structures = ["cell", "bacteria", "virus", "protein"]
target = "enzyme"
```

**Output:**
```
Structure 'enzyme' not found. Total structures examined: 4.
```

---

## 🔧 Implementation Hints

- Use array search methods to locate the target structure
- Remember to convert array index to user-friendly position (add 1)
- Handle both success and failure cases appropriately
- Ensure the output string matches the exact format specified

---

## ✨ Key Takeaways

This challenge helps you practice:

- 🔍 Searching through arrays
- 📊 Data analysis and reporting
- 🎨 String formatting and interpolation
- 🧮 Index manipulation and conversion

---

**Good luck with your analysis! 🚀**
