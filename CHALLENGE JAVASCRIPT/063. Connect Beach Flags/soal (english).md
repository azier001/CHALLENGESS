# 🏖️ Connect Beach Flags Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function named `connectBeachFlags` that connects an array of beach flags into a single string, simulating flags tied together on a windy day at the beach.

---

## 🎯 Objective

Your task is to connect all beach flags in the order they appear in the array, using the string `"--"` as a connector between each flag.

---

## 🔧 Function Specification

### Function Name
```javascript
connectBeachFlags(flags)
```

### Parameters
- **`flags`** *(string-array)*: An array of strings where each string represents a beach flag

### Return Value
- **Type:** `string`
- **Description:** A string representing all beach flags connected together in order, separated by `"--"`

---

## 💡 Examples

| Input | Output |
|-------|--------|
| `["red", "blue", "green"]` | `"red--blue--green"` |
| `["yellow", "red"]` | `"yellow--red"` |
| `["pink"]` | `"pink"` |

### Example Breakdown

```javascript
// Multiple flags
connectBeachFlags(["red", "blue", "green"])
// Result: "red--blue--green"

// Two flags
connectBeachFlags(["yellow", "red"])
// Result: "yellow--red"

// Single flag
connectBeachFlags(["pink"])
// Result: "pink"
```

---

## 🛠️ Implementation Approach

To solve this challenge, you can use:

- **Array manipulation** techniques
- **String concatenation** methods
- **Iteration** through the array of flags

### Key Considerations

> ⚠️ **Important:** Handle the special case when there is only one flag in the array (no connectors needed)

---

## 🎨 Visual Representation

```
Input:  ["red", "blue", "green"]
        
Process: red + "--" + blue + "--" + green

Output: "red--blue--green"
```

---

## 🏁 Success Criteria

Your function should:
- ✅ Connect all flags in the correct order
- ✅ Use `"--"` as the connector string
- ✅ Handle single flag arrays properly
- ✅ Return a properly formatted string
