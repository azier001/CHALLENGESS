# Mountain Stream Fish Observation Report

## 📋 Challenge Overview

**Difficulty Level:** Easy

Create a function that combines unusual fish species with common mountain stream fish and generates a beautifully formatted observation report.

---

## 🎯 Objective

Implement a function named `fishObservation` that receives two parameters and produces a comprehensive observation report including greeting, temperature data, fish species list, and ecological facts.

---

## 📝 Function Requirements

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `unusualFish` | Array | An array of strings representing unusual fish species names |
| `waterTemp` | Number | Water temperature in Celsius |

### Return Value

A **string** containing the formatted observation report

---

## 🔧 Implementation Steps

### Step 1: Concatenate Fish Arrays
- Combine the `unusualFish` array with a predefined array of common mountain stream fish
- Common species reference: `["trout", "salmon", "grayling"]`

### Step 2: Create Formatted String
The output report must include the following sections:

- **Morning Greeting** — A welcoming message to start the report
- **Water Temperature** — Display the current water temperature in Celsius
- **Fish Species List** — All observed fish (unusual + common), joined with commas and spaces
- **Fun Fact** — An interesting fact about mountain stream ecosystems

---

## 📌 Key Notes

- ✅ Join all fish species with **commas and spaces** for optimal readability
- ✅ Ensure the output string is well-formatted and easy to read
- ✅ Include both unusual and common fish species in the final list
- ✅ Present data in a clear, organized manner

---

## 💡 Example Usage

```javascript
const unusualSpecies = ["electric eel", "arapaima"];
const temperature = 12;

fishObservation(unusualSpecies, temperature);
```

**Expected Output Format:**

```
Good morning! 🌅

Today's Water Temperature: 12°C

Fish Species Observed:
electric eel, arapaima, trout, salmon, grayling

Fun Fact:
Mountain stream ecosystems are home to some of the most resilient fish species on Earth, adapted to cold, fast-flowing waters.
```

---

## 🌊 Context

Mountain streams are pristine aquatic environments characterized by cold, clear, fast-flowing waters. These ecosystems support diverse fish populations ranging from common species like trout and salmon to more unusual species found in specific geographic regions. Your observation report will help document and celebrate the biodiversity of these remarkable environments.

---

## ✨ Challenge Success Criteria

- ✅ Function accepts `unusualFish` array and `waterTemp` number
- ✅ Common fish array is properly concatenated
- ✅ Output includes all required sections
- ✅ Fish species are comma-separated with proper spacing
- ✅ Return value is a single formatted string
