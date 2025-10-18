# 🌿 Moss Age Classification Challenge

## 📋 Overview

**Difficulty Level:** `Easy`

As a nature photographer exploring a dense forest, you've encountered various moss-covered rocks. Your task is to classify the moss based on its age by implementing a classification function.

---

## 🎯 Challenge Description

Create a function named **`classifyMoss`** that receives `mossAge` as its parameter and returns a string describing the type of moss according to its age classification.

---

## 📊 Classification Rules

The moss should be classified according to the following age ranges:

| Age Range (years) | Classification |
|-------------------|----------------|
| 0 - 5 | **Young Moss** |
| 6 - 20 | **Mature Moss** |
| 21 - 50 | **Old Moss** |
| 51 - 100 | **Ancient Moss** |
| Over 100 | **Legendary Moss** |

---

## 🔧 Function Specification

### Function Name
```
classifyMoss
```

### Parameter
- **`mossAge`** (number): An integer representing the age of the moss in years.

### Return Value
- A **string** representing the classification of the moss based on its age.

---

## 💡 Example Usage

```javascript
classifyMoss(3);    // Returns: "Young Moss"
classifyMoss(15);   // Returns: "Mature Moss"
classifyMoss(35);   // Returns: "Old Moss"
classifyMoss(75);   // Returns: "Ancient Moss"
classifyMoss(150);  // Returns: "Legendary Moss"
```

---

## ✅ Implementation Checklist

- [ ] Function accepts `mossAge` parameter
- [ ] Correctly identifies age range 0-5 years
- [ ] Correctly identifies age range 6-20 years
- [ ] Correctly identifies age range 21-50 years
- [ ] Correctly identifies age range 51-100 years
- [ ] Correctly identifies ages over 100 years
- [ ] Returns appropriate string for each classification

---

## 🌲 Happy Coding!

Good luck with your moss classification adventure!
