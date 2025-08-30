# 🏖️ Safe Sunbathing Spot Finder

## 📋 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function that helps beachgoers determine if a spot is safe for sunbathing based on environmental conditions.

---

## 🎯 Objective

Implement a function named `sunbathingSpot` that evaluates beach safety conditions using temperature readings and spider count observations.

### Function Signature
```javascript
function sunbathingSpot(temperature, spiderCount)
```

---

## 📝 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `temperature` | `number` | Temperature in degrees Celsius (always an integer) |
| `spiderCount` | `number` | Number of spiders spotted nearby (non-negative integer) |

---

## 🔍 Safety Evaluation Criteria

The function should evaluate conditions using the following priority system:

### 🕷️ **Spider Count (Higher Priority)**
- **0 spiders** → Continue to temperature check
- **1-2 spiders** → Return `"Be cautious!"`
- **3+ spiders** → Return `"Find another spot!"`

### 🌡️ **Temperature Range (Lower Priority)**
- **25-30°C (inclusive)** → Return `"Perfect spot!"` *(only if 0 spiders)*
- **Above 30°C** → Return `"Too hot!"`
- **Below 25°C** → Return `"Too cold!"`

---

## ⚠️ Important Note

> **Spider count takes precedence over temperature!**
> 
> Even if the temperature is in the perfect range, the presence of spiders will override the temperature-based decision.

---

## 📤 Expected Return Values

The function returns one of the following strings:

- `"Perfect spot!"` - Ideal conditions (25-30°C, no spiders)
- `"Too hot!"` - Temperature above 30°C
- `"Too cold!"` - Temperature below 25°C
- `"Be cautious!"` - 1-2 spiders present
- `"Find another spot!"` - 3 or more spiders present

---

## 💡 Example Test Cases

```javascript
// Perfect conditions
sunbathingSpot(27, 0) // → "Perfect spot!"

// Temperature issues
sunbathingSpot(35, 0) // → "Too hot!"
sunbathingSpot(20, 0) // → "Too cold!"

// Spider warnings (override temperature)
sunbathingSpot(28, 2) // → "Be cautious!"
sunbathingSpot(27, 5) // → "Find another spot!"
```

---

## 🚀 Getting Started

1. Create the function with the specified name and parameters
2. Implement the spider count check first (higher priority)
3. Add temperature range validation as fallback
4. Test with various input combinations
5. Ensure all return values match exactly as specified

**Happy coding! 🌞**
