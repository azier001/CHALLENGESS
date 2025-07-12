# 📸 Photo Effect Processor

## 🎯 Challenge Overview

**Difficulty Level:** `Easy`

Create a powerful photo processing function that applies various effects to image data arrays with customizable intensity levels.

---

## 📋 Requirements

### Function Specification

```javascript
function processPhoto(photoData, effectType, intensity)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `photoData` | `Array<number>` | Array of integers representing photo data |
| `effectType` | `string` | Type of effect to apply to the photo |
| `intensity` | `number` | Intensity level for certain effects |

### Return Value

- **Type:** `Array<number>`
- **Description:** Modified photo data array after applying the specified effect

---

## ⚡ Effect Types

### 🔄 Reverse Effect
- **Trigger:** `effectType === "Reverse"`
- **Action:** Reverse the order of elements in the `photoData` array
- **Intensity:** Not used for this effect

### 🔊 Amplify Effect
- **Trigger:** `effectType === "Amplify"`
- **Action:** Multiply each element in `photoData` by the `intensity` value
- **Intensity:** Multiplier value applied to each element

### 🚫 Default Behavior
- **Trigger:** Any other `effectType` value
- **Action:** Return the original `photoData` array unchanged
- **Intensity:** Not used for this effect

---

## 💡 Implementation Guidelines

### Key Points to Remember

- ✅ Handle the three main effect types: `"Reverse"`, `"Amplify"`, and default
- ✅ Use the `intensity` parameter only for the "Amplify" effect
- ✅ Return the original array for unrecognized effect types
- ✅ Ensure the function returns an array of numbers

### Expected Behavior

```javascript
// Example usage patterns
processPhoto([1, 2, 3, 4], "Reverse", 0);     // Should reverse array
processPhoto([2, 4, 6], "Amplify", 3);        // Should multiply by 3
processPhoto([1, 2, 3], "Unknown", 5);        // Should return original
```

---

## 🎨 Visual Summary

```
Input: photoData[] + effectType + intensity
         ↓
    ┌─────────────────────────────────────┐
    │        processPhoto()               │
    │                                     │
    │  ┌─────────────┐  ┌─────────────┐   │
    │  │  "Reverse"  │  │  "Amplify"  │   │
    │  │     ↓       │  │     ↓       │   │
    │  │  Reverse    │  │  Multiply   │   │
    │  │   Order     │  │  by Intensity│   │
    │  └─────────────┘  └─────────────┘   │
    │         ↓               ↓           │
    │  ┌─────────────────────────────────┐ │
    │  │        Modified Array          │ │
    │  └─────────────────────────────────┘ │
    └─────────────────────────────────────┘
         ↓
    Output: Modified photoData[]
```

---

## 🏆 Success Criteria

Your implementation should successfully:

1. **Process Reverse Effect** - Correctly reverse array element order
2. **Process Amplify Effect** - Properly multiply each element by intensity
3. **Handle Unknown Effects** - Return original array for unrecognized effects
4. **Maintain Data Types** - Ensure output remains an array of numbers

---

*Good luck with your implementation! 🚀*
