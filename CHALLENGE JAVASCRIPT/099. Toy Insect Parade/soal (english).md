# 🐛 Toy Insect Parade Challenge

> **Difficulty Level:** `Easy` 🟢

## 📋 Challenge Overview

Create a whimsical function that simulates a parade of toy insects in a child's playroom! Your task is to build the `toyInsectParade` function that creates a delightful formatted string representing marching toy insects.

---

## 🎯 Function Requirements

### Function Signature
```javascript
function toyInsectParade(insects, repeatCount)
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `insects` | `Array<string>` | An array of strings representing different toy insects |
| `repeatCount` | `number` | Integer specifying how many times each insect appears in the parade |

### Return Value
- **String**: Formatted parade representation
- **Special case**: `"No parade today!"` when conditions aren't met

---

## 🎪 Parade Format

The parade follows this structure:
```
Start -> [insect parade] -> Finish
```

### Rules:
- 🚀 **Start marker**: Always begins with `"Start"`
- 🔄 **Repetition**: Each insect appears `repeatCount` times consecutively  
- 🏹 **Separator**: Elements are connected with ` -> `
- 🏁 **End marker**: Always concludes with `"Finish"`

---

## ✨ Examples

### Example 1: Normal Parade
**Input:**
```javascript
insects = ["ant", "butterfly", "ladybug"]
repeatCount = 2
```

**Output:**
```javascript
"Start -> ant -> ant -> butterfly -> butterfly -> ladybug -> ladybug -> Finish"
```

### Example 2: Single Repetition
**Input:**
```javascript
insects = ["bee", "cricket"]  
repeatCount = 1
```

**Output:**
```javascript
"Start -> bee -> cricket -> Finish"
```

### Example 3: No Parade Scenarios
**Input:**
```javascript
insects = []           // Empty array
repeatCount = 2
```
**Output:**
```javascript
"No parade today!"
```

**Input:**
```javascript
insects = ["ant"]      // Zero or negative repeat count
repeatCount = 0
```
**Output:**
```javascript
"No parade today!"
```

---

## ⚠️ Edge Cases to Handle

- 📭 **Empty insect array** (`[]`)
- 🚫 **Zero repeat count** (`repeatCount = 0`)  
- ➖ **Negative repeat count** (`repeatCount < 0`)

> **Important:** All edge cases should return `"No parade today!"`

---

## 🎨 Implementation Guidelines

- ✅ **Line limit**: Keep your solution within **10-19 lines**
- 🧪 **Testing**: Verify all edge cases work correctly
- 🎯 **Focus**: Clean, readable code that handles all requirements
- 🔍 **Validation**: Ensure proper input validation

---

## 🏆 Success Criteria

Your function should:
1. ✅ Handle normal parade scenarios correctly
2. ✅ Manage all specified edge cases  
3. ✅ Return properly formatted strings
4. ✅ Stay within the line limit
5. ✅ Be clean and maintainable

Happy coding! 🎉
