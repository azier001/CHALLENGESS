# 🎨 Craft Fair Organization

## Challenge Level
**Easy** ⭐

---

## 📋 Overview

Write a function `organizeFairSchedule` that manages craft fair logistics by updating display counts and consolidating event schedules.

---

## 🎯 Function Specification

### Function Name
```javascript
organizeFairSchedule(basketCount, textileCount, musicianSlots, belfryChimes)
```

### Description
The function performs two main operations:
1. **Increments** the basket and textile display counts by 1
2. **Concatenates** musician performance slots with belfry chime times into a unified schedule array

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `basketCount` | `number` | Current number of basket displays |
| `textileCount` | `number` | Current number of textile displays |
| `musicianSlots` | `array` | Array of musician performance times |
| `belfryChimes` | `array` | Array of belfry chime times |

---

## 📤 Return Value

**Type:** `Object`

**Structure:**
```javascript
{
  baskets: number,
  textiles: number,
  schedule: array
}
```

### Return Object Properties

- **`baskets`** — Updated basket count (original + 1)
- **`textiles`** — Updated textile count (original + 1)
- **`schedule`** — Combined array of musician slots and belfry chimes

---

## 💡 Example Usage

```javascript
// Input
organizeFairSchedule(5, 8, ["10:00", "14:00"], ["12:00", "16:00"])

// Output
{
  baskets: 6,
  textiles: 9,
  schedule: ["10:00", "14:00", "12:00", "16:00"]
}
```

---

## ✅ Key Requirements

- ✓ Increment both `basketCount` and `textileCount` by exactly 1
- ✓ Maintain the original order when combining arrays (musicians first, then chimes)
- ✓ Return an object with the exact property names: `baskets`, `textiles`, `schedule`
- ✓ Ensure the schedule array includes all elements from both input arrays

---

## 🔍 Implementation Notes

- Use array concatenation methods to combine the schedule arrays
- Ensure immutability by not modifying the original input parameters
- Handle edge cases such as empty arrays gracefully

---

**Good luck! 🚀**
