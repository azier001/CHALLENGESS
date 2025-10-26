# 🧬 Sort Amino Acids Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that sorts amino acids alphabetically while filtering out invalid entries.

---

## 🎯 Objective

Implement a function named **`sortProtein`** that:

1. Receives an **array of strings** representing amino acids
2. Sorts the amino acids **alphabetically**
3. Returns the **sorted array**
4. **Skips invalid amino acids** and continues sorting valid ones

---

## ✅ Valid Amino Acids

The function should recognize the following **20 standard amino acids**:

- **Alanine**
- **Arginine**
- **Asparagine**
- **Aspartic acid**
- **Cysteine**
- **Glutamic acid**
- **Glutamine**
- **Glycine**
- **Histidine**
- **Isoleucine**
- **Leucine**
- **Lysine**
- **Methionine**
- **Phenylalanine**
- **Proline**
- **Serine**
- **Threonine**
- **Tryptophan**
- **Tyrosine**
- **Valine**

---

## 📝 Function Signature

```javascript
function sortProtein(aminoAcids) {
  // Your implementation here
}
```

---

## 💡 Requirements

| Requirement | Description |
|------------|-------------|
| **Input** | Array of strings (amino acid names) |
| **Output** | Sorted array of valid amino acids |
| **Validation** | Filter out invalid amino acids |
| **Sorting** | Alphabetical order (A-Z) |

---

## 🧪 Example Usage

```javascript
// Example 1: All valid amino acids
sortProtein(['Glycine', 'Alanine', 'Valine']);
// Expected output: ['Alanine', 'Glycine', 'Valine']

// Example 2: Mixed valid and invalid
sortProtein(['Glycine', 'InvalidAcid', 'Alanine', 'Unknown', 'Valine']);
// Expected output: ['Alanine', 'Glycine', 'Valine']

// Example 3: Empty array
sortProtein([]);
// Expected output: []
```

---

## 🔑 Key Points

> **Note:** The function should be case-sensitive and match the amino acid names exactly as listed above.

- ✨ Only the 20 standard amino acids are considered valid
- 🔍 Invalid entries should be silently ignored
- 📊 Return an empty array if no valid amino acids are found
- 🎨 Maintain alphabetical sorting for the output

---

## 🚀 Getting Started

Think about:
- How to validate amino acids efficiently
- The best sorting approach for strings
- Edge cases (empty arrays, all invalid entries, duplicates)

Good luck! 🍀
