# 🌿 Botanical Specimen Analysis

## 🧪 Challenge

**Difficulty:** Easy

Create a function named `analyzePlantSpecimen` that receives `plantName`, `numberOfLeaves`, and `plantHeight` as its parameters.

The function should analyze a plant specimen and return a formatted string with information about the plant.

---

## ✅ Instructions

Follow these steps to create the analysis:

1. **Calculate the area of a single leaf:**

   * Assume each leaf is rectangular with a width of `1.5 cm`.
   * Formula: `leafArea = plantHeight * 1.5`

2. **Calculate the total leaf area:**

   * Multiply the single leaf area by the number of leaves.

3. **Convert plant height to inches:**

   * Use the formula: `heightInInches = plantHeight / 2.54`
   * Round the result to one decimal place.

4. **Classify the plant height:**

   * If height < 30 cm → `"short"`
   * If 30 cm ≤ height ≤ 100 cm → `"medium"`
   * If height > 100 cm → `"tall"`

5. **Create a color code:**

   * Repeat the first letter of the plant name three times (e.g., "Fern" → "FFF").

6. **Return a formatted string** with all calculated values.

---

## 📥 Parameters

| Name             | Type   | Description                             |
| ---------------- | ------ | --------------------------------------- |
| `plantName`      | String | The name of the plant specimen.         |
| `numberOfLeaves` | Number | The number of leaves on the plant.      |
| `plantHeight`    | Number | The height of the plant in centimeters. |

---

## 📤 Return Value

A formatted string containing:

* Plant name
* Number of leaves
* Plant height in cm and inches
* Single leaf area
* Total leaf area
* Height classification
* Color code

---

## 💡 Example

```javascript
analyzePlantSpecimen("Moss", 5000, 2);
```

### ✅ Output

```
Plant: Moss
Number of Leaves: 5000
Plant Height: 2 cm (0.8 inches)
Leaf Area: 3.00 sq cm
Total Leaf Area: 15000.00 sq cm
Height Classification: short
Color Code: MMM
```

---

Good luck! 🍀
