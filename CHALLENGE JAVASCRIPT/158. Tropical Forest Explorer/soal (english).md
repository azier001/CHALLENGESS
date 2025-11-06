# 🌴 Tropical Forest Explorer

## Challenge Level
**Easy** 🟢

---

## 📋 Overview

Create a function named `exploreForest` that simulates a nature enthusiast's journey through a tropical forest. The function tracks daily observations of birds and plants, ensuring each observation is unique.

---

## 🎯 Challenge Description

The nature enthusiast explores a tropical forest over several days, alternating between observing birds and plants:

- **Odd-numbered days** (1, 3, 5, ...) → Observe a **bird** 🦜
- **Even-numbered days** (2, 4, 6, ...) → Observe a **plant** 🌿

### Important Rules:
- Each observation is added to the result array **only if it hasn't been observed before**
- The function continues for the specified number of exploration days
- Observations alternate between birds and plants based on the day number

---

## 🔧 Function Signature

```javascript
function exploreForest(birds, plants, explorationDays) {
  // Your implementation here
}
```

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `birds` | `array` | An array of strings representing different bird species in the forest |
| `plants` | `array` | An array of strings representing different plant types in the forest |
| `explorationDays` | `number` | An integer representing the number of days spent exploring |

---

## 📤 Return Value

**Type:** `array`

An array of strings containing the nature enthusiast's **unique daily observations**.

---

## 💡 Example Usage

```javascript
const birds = ['Toucan', 'Macaw', 'Parrot', 'Eagle'];
const plants = ['Orchid', 'Fern', 'Bamboo', 'Moss'];
const days = 7;

const observations = exploreForest(birds, plants, days);
// Expected output: Array of unique observations alternating between birds and plants
```

---

## 🔍 Key Concepts

- **Alternating Pattern**: Use day number to determine whether to observe birds or plants
- **Uniqueness**: Track previously observed species to avoid duplicates
- **Array Iteration**: Cycle through available birds and plants
- **Conditional Logic**: Odd vs. even day determination

---

## ✅ Success Criteria

Your function should:
- ✓ Correctly alternate between birds and plants based on day number
- ✓ Prevent duplicate observations
- ✓ Return an array with the correct number of unique observations
- ✓ Handle edge cases (empty arrays, zero days, etc.)

---

**Happy Coding!** 🚀
