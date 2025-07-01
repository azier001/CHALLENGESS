# Chemical Formula Decoder Challenge

## 🧪 Problem Overview

**Difficulty Level:** Easy

In a dimly lit laboratory, a scientist is trying to decode mysterious chemical formulas. Your task is to help the scientist by creating a function that decodes these formulas.

## 📋 Task Description

Create a function named `decodeChemicalFormula` that receives `codedFormula` as its parameter.

### Function Signature
```javascript
function decodeChemicalFormula(codedFormula) {
    // Your implementation here
}
```

## 🔬 Decoding Rules

The function should decode the input string by applying the following transformation rules:

- **'a'** → **'H'** (Hydrogen)
- **'b'** → **'O'** (Oxygen)  
- **'c'** → **'C'** (Carbon)
- **'d'** → **'N'** (Nitrogen)
- **'e'** → **'Cl'** (Chlorine)
- **Any other lowercase letter** → **Capitalize it**

## ⚗️ Processing Steps

1. **Decode** the input string using the rules above
2. **Count** the occurrences of each element
3. **Add subscripts** for elements that appear more than once

> **Note:** If an element appears more than once, add a subscript number after it.

## 📥 Parameters

- **`codedFormula`** *(string)*: A string representing the coded chemical formula
  - Will only contain lowercase letters
  - Represents the mysterious formula to be decoded

## 📤 Return Value

- **Returns:** A string representing the decoded chemical formula with proper element symbols and subscripts

## 🎯 Example Scenarios

### Input Processing Flow:
```
Input: "aabbc"
↓
Decode: "H" + "H" + "O" + "O" + "C"
↓
Count: H(2), O(2), C(1)
↓
Output: "H2O2C"
```

### Another Example:
```
Input: "abcde" 
↓
Decode: "H" + "O" + "C" + "N" + "Cl"
↓
Count: All appear once
↓
Output: "HOCNCl"
```

## 🧬 Chemical Elements Reference

| Code | Element | Symbol | Name |
|------|---------|--------|------|
| a | H | Hydrogen | Most abundant element |
| b | O | Oxygen | Essential for life |
| c | C | Carbon | Basis of organic chemistry |
| d | N | Nitrogen | Makes up 78% of atmosphere |
| e | Cl | Chlorine | Halogen element |

---

*Good luck helping the scientist decode those mysterious formulas! 🔬✨*
