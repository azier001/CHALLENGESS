# 🐚 Paleontologist's Seashell Catalog Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that helps a paleontologist organize their seashell discoveries into a comprehensive catalog system.

---

## 🎯 Objective

Implement a function named `processSeashells` that simulates a paleontologist's examination of ancient seashells found on a beach. The function should process seashell data by reversing, concatenating, and cataloging the findings.

---

## 🔧 Function Specification

### Function Signature
```javascript
function processSeashells(seashells, keyword)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `seashells` | `Array<string>` | An array of strings, where each string represents a unique seashell name found by the paleontologist |
| `keyword` | `string` | A string representing a term of interest to the paleontologist |

---

## 📝 Requirements

The function must perform the following operations **in order**:

1. **🔄 Reverse** the order of seashell names in the array
2. **🔗 Concatenate** all seashell names into a single string
   - Use a hyphen (`-`) as the separator between each name
3. **➕ Append** the `keyword` to the end of the concatenated string
   - Use an underscore (`_`) to separate the keyword from the concatenated names

---

## 📤 Return Value

- **Type:** `string`
- **Description:** A processed seashell catalog with the appended keyword

---

## 💡 Example

### Input:
```javascript
const seashells = ["Conch", "Scallop", "Whelk", "Oyster"];
const keyword = "Atlantic";
```

### Processing Steps:
1. **Reverse:** `["Oyster", "Whelk", "Scallop", "Conch"]`
2. **Concatenate:** `"Oyster-Whelk-Scallop-Conch"`
3. **Append keyword:** `"Oyster-Whelk-Scallop-Conch_Atlantic"`

### Expected Output:
```javascript
"Oyster-Whelk-Scallop-Conch_Atlantic"
```

---

## 🔍 Key Points to Remember

- ✅ The order of operations is crucial
- ✅ Use specific separators: `-` for seashells, `_` for keyword
- ✅ Handle edge cases (empty arrays, empty strings)
- ✅ Ensure the function returns a string

---

## 🏷️ Tags

`Array Manipulation` • `String Processing` • `Data Organization` • `Algorithm Practice`
