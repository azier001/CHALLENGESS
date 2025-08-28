# 🌱 Plant Growth Tracker

## 📊 Challenge Overview

**Difficulty Level:** `Easy`  
**Domain:** Agricultural Research & Plant Embryology  
**Function Name:** `updatePlantGrowth`

---

## 🎯 Objective

Create a system that tracks the growth stages of various plants for an agricultural research center. Scientists need to monitor plant development from seed to harvest, and your function will help automate the stage progression tracking.

---

## 🔧 Function Specification

### Function Signature
```javascript
function updatePlantGrowth(plantInfo)
```

### Parameters
- **`plantInfo`** *(string)*: Input string in the format `"PlantName:Stage"`
  - `PlantName`: Name of the plant being tracked
  - `Stage`: Single-digit number (0-9) representing current growth stage

---

## ⚙️ Function Requirements

The `updatePlantGrowth` function must perform the following operations:

1. **Extract Information**
   - Parse the plant name from the input string
   - Extract the current growth stage number

2. **Update Growth Stage**
   - Increment the growth stage by 1
   - **Exception:** If stage is already 9 (fully grown), keep it at 9

3. **Add Stage Description**
   - Map the new stage number to its corresponding description
   - Format the output with the updated information

4. **Return Result**
   - Return formatted string: `"PlantName:NewStage - Description"`

---

## 🌿 Growth Stage Reference

| Stage | Description | Plant Development Phase |
|-------|-------------|------------------------|
| **0** | Seed | Initial dormant state |
| **1** | Germination | Seed begins to sprout |
| **2** | Seedling | Young plant emerges |
| **3** | Vegetative | Leaves and stems develop |
| **4** | Budding | Flower buds form |
| **5** | Flowering | Flowers bloom |
| **6** | Pollination | Reproductive process |
| **7** | Fruit development | Fruits begin forming |
| **8** | Ripening | Fruits mature |
| **9** | Harvest-ready | Fully mature, ready for harvest |

---

## 📝 Input/Output Format

### Input Format
```
"PlantName:Stage"
```

### Output Format
```
"PlantName:NewStage - Description"
```

### Example Flow
```
Input:  "Tomato:3"
Output: "Tomato:4 - Budding"
```

---

## 🧪 Test Scenarios

Consider testing with these scenarios:
- **Early stage progression:** `"Carrot:0"` → `"Carrot:1 - Germination"`
- **Mid-stage development:** `"Rose:5"` → `"Rose:6 - Pollination"`
- **Maximum stage handling:** `"Apple:9"` → `"Apple:9 - Harvest-ready"`
- **Various plant names:** Different plant species at different stages

---

## 🎯 Success Criteria

Your function should:
- ✅ Correctly parse the input string format
- ✅ Handle stage progression logic accurately
- ✅ Apply proper stage descriptions
- ✅ Maintain stage 9 as the maximum (no overflow)
- ✅ Return properly formatted output strings
- ✅ Work with any valid plant name and stage combination
