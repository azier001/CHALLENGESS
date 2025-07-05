# 🌿 Nature's Energy Sequence Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

As a scientist exploring nature's hidden corners, you've developed a system to track your energy levels while observing different natural elements. Your task is to implement this energy tracking system in code.

## 🎯 Objective

Create a function named `exploreNatureSequence` that processes a sequence of nature elements and calculates the final energy level based on specific rules.

## 🔧 Function Specification

### Function Signature
```javascript
function exploreNatureSequence(sequence, energy)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `sequence` | `string` | A string representing a sequence of nature elements |
| `energy` | `number` | An integer representing the scientist's initial energy level |

### Nature Elements

The sequence consists of the following characters, each representing a different natural element:

- **🌸 `F`** - Flower
- **🪨 `R`** - Rock  
- **🌳 `T`** - Tree
- **🍃 `L`** - Leaf

## ⚡ Energy Calculation Rules

The function processes the sequence and modifies energy levels according to these rules:

### 1. Adjacent Element Comparison
- **Same elements:** `energy + 1`
- **Different elements:** `energy - 1`

### 2. Flower Bonus
- **Flower element (`F`):** `energy + 2`

> **Note:** These rules are applied as you traverse through the sequence, comparing each element with its adjacent neighbor.

## 📤 Return Value

The function returns a **number** representing the final energy level after exploring the entire sequence.

## 💡 Example Walkthrough

```javascript
// Example sequence: "FRT"
// Initial energy: 10

// Step 1: F (Flower) → energy + 2 = 12
// Step 2: F vs R (different) → energy - 1 = 11  
// Step 3: R vs T (different) → energy - 1 = 10
// Final energy: 10
```

## 🎨 Implementation Tips

- Process the sequence character by character
- Keep track of the previous element for comparison
- Apply the flower bonus whenever you encounter an 'F'
- Handle edge cases (empty sequences, single elements)

## 🧪 Testing Considerations

Consider testing with:
- Empty sequences
- Single element sequences
- Sequences with repeated elements
- Sequences with all different elements
- Sequences containing multiple flowers

---

*Happy coding, nature explorer! 🌲✨*
