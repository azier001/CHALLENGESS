# 🦕 Dinosaur Bone Extraction Challenge

## Difficulty Level
**Easy** ⭐

---

## 📋 Challenge Overview

Help paleontologists at the natural history museum extract specific bones from a dinosaur skeleton for closer study! Your task is to create a function that selectively retrieves bone segments from a complete skeleton array.

---

## 🎯 Objective

Create a function named `extractBoneStructure` that receives three parameters and returns a new array containing only the selected bones from the specified range.

---

## 📥 Function Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `dinosaurBones` | `array` | An array of strings representing different bones in a dinosaur skeleton |
| `startPosition` | `number` | The starting index for extraction **(inclusive)** |
| `endPosition` | `number` | The ending index for extraction **(inclusive)** |

---

## 📤 Return Value

The function should return a **new array** containing the extracted bones from the specified positions.

---

## 🔧 Implementation Requirements

- Use **array slicing** to extract the specified bones
- Extract bones starting from `startPosition` up to and **including** `endPosition`
- Return a new array without modifying the original `dinosaurBones` array

---

## 💡 Key Points to Remember

- ✅ Start position is **inclusive**
- ✅ End position is **inclusive**
- ✅ Use array slicing method
- ✅ Return a new array
- ✅ Do not modify the original array

---

## 📝 Function Signature

```javascript
function extractBoneStructure(dinosaurBones, startPosition, endPosition) {
  // Your code here
}
```

---

## 🧪 Example Usage

```javascript
const skeleton = ['skull', 'vertebra', 'rib', 'femur', 'tibia', 'claw'];
const extracted = extractBoneStructure(skeleton, 1, 3);

console.log(extracted);
// Expected output: ['vertebra', 'rib', 'femur']
```

---

## 🎓 Learning Objectives

- Understanding array slicing operations
- Working with inclusive index ranges
- Extracting subarrays without mutation
- Applying practical array methods

---

**Good luck, paleontologist! 🦴🔬**
