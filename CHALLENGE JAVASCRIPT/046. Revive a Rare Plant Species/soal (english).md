# 🌿 Revive a Rare Plant Species

## 🎯 Challenge Overview

**Difficulty Level:** `Easy`

As a botanist on a quest to save a rare plant species in a remote forest, you've discovered that reversing the plant's DNA sequence can rejuvenate it and prevent extinction. Your mission is to implement a function that reverses the given DNA sequence while maintaining its specific format.

---

## 🧬 The Science Behind It

The DNA sequence is represented as a string of nucleotide bases:
- **A** (Adenine)
- **T** (Thymine) 
- **C** (Cytosine)
- **G** (Guanine)

These bases are grouped in sets of four, separated by spaces, mimicking the structure of genetic codons.

---

## 📋 Task Requirements

### Function Specification

Create a function named `reviveRarePlant` that:

- **Function Name:** `reviveRarePlant`
- **Parameter:** `dnaSequence` (string)
- **Returns:** Modified DNA sequence (string)

### Input Format
- String of uppercase letters (A, T, C, G)
- Grouped in sets of four characters
- Each group separated by spaces
- Example: `'ATCG TGCA GCTA'`

### Output Format
- Reversed DNA sequence
- Maintains original grouping structure
- Preserves spacing between groups
- Example: `'ATCG ACGT GCTA'`

---

## 💡 Example

### Input
```
'ATCG TGCA GCTA'
```

### Expected Output
```
'ATCG ACGT GCTA'
```

### Explanation
The function reverses the entire sequence while keeping the 4-character grouping and space separation intact.

---

## 🔬 Implementation Guidelines

1. **Preserve Structure:** Maintain the original grouping of 4 characters
2. **Reverse Logic:** Apply reversal to the entire sequence
3. **Format Consistency:** Keep spaces between groups
4. **Case Sensitivity:** Work with uppercase letters only

---

## 🌟 Success Criteria

- ✅ Function correctly reverses the DNA sequence
- ✅ Maintains original grouping format
- ✅ Preserves spacing between groups
- ✅ Handles various input lengths
- ✅ Returns properly formatted string

---

## 🚨 Mission Critical

> **Remember:** The fate of the rare plant species rests in your hands! Your implementation will determine whether this endangered species can be saved from extinction.

**Good luck, botanist!** 🔬🌱

---

*Challenge Category: String Manipulation | Difficulty: Easy | Theme: Bioinformatics*
