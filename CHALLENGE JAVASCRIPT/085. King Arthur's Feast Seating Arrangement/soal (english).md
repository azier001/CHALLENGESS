# 🏰 King Arthur's Feast Seating Arrangement

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a medieval seating arrangement for King Arthur's legendary round table feast! This challenge involves organizing knights and wine goblets in a specific alternating pattern around the table.

---

## 🎯 Objective

Design a function that creates a seating arrangement where every other position at the round table has a goblet of wine, ensuring a perfect alternating pattern between knights and wine.

---

## 🛡️ Function Specification

### Function Name
```javascript
feastArrangement(numKnights)
```

### Parameters
- **`numKnights`** *(number)*: The total number of knights attending King Arthur's feast

### Return Value
- **Array of strings**: Representing the complete seating arrangement
- Each element is either:
  - `"knight"` - representing a seated knight
  - `"wine"` - representing a goblet of wine

---

## 📐 Requirements

### Core Rules
1. **Alternating Pattern**: The seating must alternate between knights and wine goblets
2. **Starting Position**: The arrangement must begin with a knight
3. **Round Table Logic**: Consider the circular nature of the seating arrangement

### Expected Pattern
```
Position 1: "knight"
Position 2: "wine" 
Position 3: "knight"
Position 4: "wine"
...and so on
```

---

## 💡 Example Scenarios

### Small Gathering (3 Knights)
```javascript
// Input: 3
// Expected Output: ["knight", "wine", "knight", "wine", "knight", "wine"]
```

### Medium Gathering (5 Knights)
```javascript
// Input: 5  
// Expected Output: ["knight", "wine", "knight", "wine", "knight", "wine", "knight", "wine", "knight", "wine"]
```

---

## 🤔 Key Considerations

- **Array Length**: The total length will be `numKnights × 2` (each knight gets a wine goblet)
- **Pattern Consistency**: Maintain the alternating sequence throughout
- **Edge Cases**: Consider scenarios with very few knights (1-2)
- **Medieval Theme**: Keep the output strings exactly as specified: `"knight"` and `"wine"`

---

## 🎭 Story Context

> *In the grand halls of Camelot, King Arthur hosts magnificent feasts at his legendary round table. To ensure proper hospitality, he mandates that every knight must have a goblet of fine wine placed beside them. Your task is to help the royal steward arrange the seating to maintain this noble tradition!*

---

**Good luck, noble programmer! May your code be as legendary as Excalibur itself! ⚔️**
