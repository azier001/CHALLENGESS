# 🌱 Garden Label Formatter

## Challenge Difficulty
**Easy** ⭐

---

## 📋 Overview

Create a function named `createGardenLabel` that generates a formatted label for a plant. The function receives information about the plant and returns a beautifully formatted string label.

---

## 🎯 Challenge Description

Your task is to implement a function that takes three parameters about a plant and returns a formatted label string.

### Function Signature
```javascript
createGardenLabel(plantName, plantAge, isFlowering)
```

---

## 📝 Label Format

The function should generate a label in the following format:

```
Plant: [plantName], Age: [plantAge] years, Flowering: [yes/no]
```

### Format Rules:
- **`[plantName]`** - Replace with the plant's name
- **`[plantAge]`** - Replace with the plant's age in years
- **`[yes/no]`** - Replace with:
  - `"yes"` if `isFlowering` is `true`
  - `"no"` if `isFlowering` is `false`

---

## 💡 Examples

### Example 1:
```javascript
createGardenLabel("Rose", 3, true)
// Output: "Plant: Rose, Age: 3 years, Flowering: yes"
```

### Example 2:
```javascript
createGardenLabel("Cactus", 5, false)
// Output: "Plant: Cactus, Age: 5 years, Flowering: no"
```

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `plantName` | `string` | The name of the plant |
| `plantAge` | `number` | The age of the plant in years (positive integer) |
| `isFlowering` | `boolean` | Indicates whether the plant is currently flowering |

---

## 📤 Return Value

**Type:** `string`

**Description:** A formatted garden label string containing the plant's information.

---

## ✅ Requirements Checklist

- [ ] Function is named `createGardenLabel`
- [ ] Accepts three parameters: `plantName`, `plantAge`, `isFlowering`
- [ ] Returns a string in the correct format
- [ ] Correctly converts boolean to "yes"/"no"
- [ ] Includes proper spacing and punctuation

---

## 🚀 Getting Started

Start by defining your function and building the label string step by step. Remember to handle the boolean conversion for the flowering status!

```javascript
function createGardenLabel(plantName, plantAge, isFlowering) {
  // Your code here
}
```

Good luck! 🌻
