# 🔬 Analyzing Plant Specimens in the Lab

<div align="center">

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen)
![Topic](https://img.shields.io/badge/Topic-Biology%20Lab-blue)
![Language](https://img.shields.io/badge/Language-JavaScript-yellow)

</div>

---

## 🎯 Challenge Overview

> **Scenario:** You're a biology student working in the campus laboratory, examining plant specimens under a microscope. Your mission is to systematically count specimens that exhibit specific characteristics.

**Task:** Create a function named `analyzePlantSpecimens` that processes specimen data and counts matches based on target characteristics.

---

## 📋 Function Specification

### **Function Name**
```javascript
analyzePlantSpecimens(specimens, targetCharacteristic)
```

### **Parameters**

| Parameter | Type | Description | Example |
|-----------|------|-------------|---------|
| `specimens` | `Array<string>` | Collection of plant specimens with their characteristics | `["green leaves, thin stem", "yellow flowers"]` |
| `targetCharacteristic` | `string` | The specific trait you're searching for | `"green leaves"` |

---

## ⚙️ Processing Requirements

### **Core Logic**
1. **🔍 Iterate** through each specimen in the array
2. **✅ Count** specimens containing the target characteristic
3. **⏭️ Skip** non-matching specimens using `continue` statement
4. **🛑 Emergency Stop** when encountering `"microscope malfunction"`
5. **📊 Return** final count of matching specimens

### **Control Flow Rules**

| Condition | Action | Statement |
|-----------|--------|-----------|
| Specimen matches target | Increment counter, proceed | Continue loop |
| Specimen doesn't match | Skip to next specimen | `continue` |
| "microscope malfunction" found | Stop immediately, return current count | `break` |

---

## 🚨 Special Conditions

> **⚠️ Important:** If the examination encounters a specimen labeled **"microscope malfunction"**, the analysis must halt immediately. This simulates real laboratory conditions where equipment failure requires stopping the procedure.

---

## 📤 Return Value

- **Type:** `number`
- **Description:** Total count of specimens matching the target characteristic
- **Note:** Count represents specimens analyzed before any malfunction occurs

---

## 🔬 Laboratory Context

This challenge simulates real scientific methodology where:
- **Systematic observation** is crucial for accurate data collection
- **Equipment reliability** affects research outcomes  
- **Proper error handling** prevents invalid results
- **Documentation standards** ensure reproducible experiments
