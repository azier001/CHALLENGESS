# 🌸 Find the Flower in the Garden

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function that searches through a garden array to find a specific flower and returns its position.

---

## 🎯 Objective

Implement a function named `findFlower` that:

- **Receives:** An array of strings (`garden`) and a target string (`flower`)
- **Returns:** The index of the first occurrence of the flower
- **Fallback:** Returns `-1` if the flower is not found

---

## 📝 Function Specification

### Function Signature
```javascript
function findFlower(garden, flower)
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `garden` | `Array<string>` | Array containing flower names |
| `flower` | `string` | The flower to search for |

### Return Value
| Type | Description |
|------|-------------|
| `number` | Index of the flower (0-based) or `-1` if not found |

---

## 💡 Examples

### Sample Garden
```javascript
const garden = [
  'roses', 
  'tulips', 
  'dandelions', 
  'sunflowers', 
  'violets', 
  'daisies', 
  'daffodils', 
  'lilies', 
  'orchids'
];
```

### Test Cases
```javascript
// ✅ Found at index 5
findFlower(garden, 'daisies');  // → 5

// ✅ Found at index 7
findFlower(garden, 'lilies');   // → 7

// ❌ Not found
findFlower(garden, 'peonies');  // → -1
```

---

## 🔍 Expected Behavior

- **Case Sensitive:** The search should be exact match
- **First Occurrence:** Return the index of the first match only
- **Zero-based Indexing:** Array indices start from 0
- **Not Found:** Return `-1` when the flower doesn't exist in the garden

---

## 🌟 Tips

- Consider using built-in array methods for efficient searching
- Remember to handle edge cases (empty arrays, null values)
- Test with various flower names to ensure accuracy

---

*Happy coding! 🚀*
