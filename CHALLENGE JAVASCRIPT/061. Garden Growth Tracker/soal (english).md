# 🌱 Garden Growth Tracker Challenge

> **Difficulty Level:** `Easy` 🟢

## 🎯 Challenge Overview

Create a function that helps a peasant family monitor their lush, chlorophyll-rich garden by tracking plant growth stages based on the number of days since planting.

---

## 📋 Function Requirements

### Function Signature
```javascript
function gardenStatus(plantType, daysGrown)
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `plantType` | `string` | The type of plant (e.g., "tomato", "carrot", "lettuce") |
| `daysGrown` | `number` | The number of days since the plant was planted |

---

## 🌿 Growth Stages & Return Values

The function should return a string describing the plant's status based on the following conditions:

| Days Range | Status | Return String |
|------------|--------|---------------|
| `< 0` | Invalid | `"Invalid number of days."` |
| `= 0` | Just Planted | `"The [plantType] seed is just planted."` |
| `1 - 10` | Sprouting | `"The [plantType] seedling is sprouting."` |
| `11 - 20` | Growing | `"The [plantType] plant is growing steadily."` |
| `21 - 30` | Mature | `"The [plantType] plant is mature and thriving."` |
| `> 30` | Ready | `"The [plantType] plant is ready for harvest!"` |

> **Note:** Replace `[plantType]` with the actual plant type in your return string.

---

## 🛠️ Implementation Guidelines

### ✅ Requirements
- Use **conditional statements** to check the `daysGrown` value
- Use **string concatenation** or **template literals** to include `plantType`
- Handle all specified growth stages properly
- Return appropriate status messages

### 💡 Tips
- Consider using `if-else` statements or `switch` cases
- Template literals (`` `string ${variable}` ``) make string interpolation easier
- Test edge cases like negative numbers and boundary values

---

## 🧪 Example Usage

```javascript
// Example function calls
gardenStatus("tomato", -1);    // "Invalid number of days."
gardenStatus("carrot", 0);     // "The carrot seed is just planted."
gardenStatus("lettuce", 5);    // "The lettuce seedling is sprouting."
gardenStatus("tomato", 15);    // "The tomato plant is growing steadily."
gardenStatus("carrot", 25);    // "The carrot plant is mature and thriving."
gardenStatus("lettuce", 35);   // "The lettuce plant is ready for harvest!"
```

---

## 🎨 Implementation Approach

1. **Validate Input**: Check if `daysGrown` is negative
2. **Check Growth Stages**: Use conditional logic to determine the appropriate stage
3. **Format Response**: Include the `plantType` in the return string
4. **Return Result**: Provide the descriptive status message

---

*Happy coding! 🌻 May your garden tracker help nurture the most vibrant digital garden!*
