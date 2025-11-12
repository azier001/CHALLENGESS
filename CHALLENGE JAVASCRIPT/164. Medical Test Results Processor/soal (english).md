# 🏥 Medical Test Results Processor

## Challenge Overview

**Difficulty Level:** `Easy`

---

## 📋 Problem Statement

In a high-tech medical production facility, a nervous patient is awaiting their test results. Your task is to process and combine the preliminary and final test results into a single, formatted report.

You need to create a function named **`processTestResults`** that transforms and merges medical test data into a comprehensive, well-structured report.

---

## 🎯 Function Specification

### Function Signature

```javascript
function processTestResults(preliminaryResults, finalResults)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `preliminaryResults` | `Array<string>` | An array of strings representing the preliminary test results |
| `finalResults` | `Array<string>` | An array of strings representing the final test results |

### Return Value

- **Type:** `Array<string>`
- **Description:** A processed array containing formatted test results with proper prefixes and separators

---

## ⚙️ Required Operations

The function must perform the following operations **in order**:

1. **Prefix Preliminary Results**  
   Add `"Status: "` prefix to each preliminary result

2. **Prefix Final Results**  
   Add `"Conclusion: "` prefix to each final result

3. **Insert Separator**  
   Add a `"---"` separator between the preliminary and final results

4. **Combine Results**  
   Concatenate all processed elements into a single array

5. **Return Processed Array**  
   Return the final formatted array of test results

---

## 💡 Example

### Input

```javascript
const preliminary = ["Blood pressure normal", "Temperature 36.5°C"];
const final = ["All tests passed", "Patient healthy"];
```

### Expected Output

```javascript
[
  "Status: Blood pressure normal",
  "Status: Temperature 36.5°C",
  "---",
  "Conclusion: All tests passed",
  "Conclusion: Patient healthy"
]
```

---

## 📝 Implementation Notes

- Maintain the order of results as they appear in the input arrays
- The separator `"---"` should appear exactly once between the two sections
- All strings should be properly formatted with their respective prefixes
- Handle empty arrays gracefully (if applicable)

---

## ✅ Success Criteria

Your implementation should:

- ✓ Correctly prefix all preliminary results with `"Status: "`
- ✓ Correctly prefix all final results with `"Conclusion: "`
- ✓ Include exactly one `"---"` separator in the correct position
- ✓ Return a single concatenated array with all formatted results
- ✓ Preserve the original order of results within each category

---

**Good luck! 🚀**
