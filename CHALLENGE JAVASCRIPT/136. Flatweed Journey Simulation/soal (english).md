# 🌾 Flatweed Journey Simulation

## Challenge Overview

**Difficulty:** `Easy`

Create a function that simulates a journey through the mystical flatweed fields. Navigate through the terrain by taking steps in various directions and track your final position!

---

## 📋 Problem Description

Implement a function named **`flatweedJourney`** that takes two parameters:

- **`steps`** (number): The number of steps to take in the journey
- **`direction`** (string): The direction of each step

### Valid Directions
- `"north"` - Move forward
- `"south"` - Move backward
- `"east"` - Horizontal movement
- `"west"` - Horizontal movement

---

## 🎯 Rules & Mechanics

### Movement Rules

| Direction | Effect on Position |
|-----------|-------------------|
| `"north"` | **Add 1** to current position |
| `"south"` | **Subtract 1** from current position |
| `"east"` | **No change** to position |
| `"west"` | **No change** to position |

### Special Rule: The Multiple of 5 Barrier

> ⚠️ **Important:** If the current position reaches a **multiple of 5** (0, 5, 10, -5, -10, etc.), the current step is **ignored** and you continue to the next step.

---

## 🔄 Function Signature

```javascript
function flatweedJourney(steps, direction) {
  // Your implementation here
}
```

---

## 📊 Expected Behavior

1. **Start** at position `0`
2. **Iterate** through the number of steps specified
3. **Apply** direction rules for each step
4. **Check** if position is a multiple of 5 before applying movement
5. **Return** the final position after all steps

---

## 💡 Example Scenarios

### Example 1: Simple North Journey
```javascript
flatweedJourney(3, "north")
// Steps: 0 → 1 → 2 → 3
// Result: 3
```

### Example 2: Multiple of 5 Encounter
```javascript
flatweedJourney(6, "north")
// Steps: 0 → 1 → 2 → 3 → 4 → (5 blocked!) → 5
// Result: 5
```

### Example 3: Mixed Directions
```javascript
flatweedJourney(4, "south")
// Steps: 0 → -1 → -2 → -3 → -4
// Result: -4
```

### Example 4: No Position Change
```javascript
flatweedJourney(5, "east")
// Steps: 0 → 0 → 0 → 0 → 0
// Result: 0
```

---

## ✅ Success Criteria

Your function should:
- ✓ Accept `steps` (number) and `direction` (string) as parameters
- ✓ Correctly implement movement for all four directions
- ✓ Skip steps when position is a multiple of 5
- ✓ Return the final position as a number
- ✓ Handle both positive and negative positions

---

## 🚀 Getting Started

Think about:
1. How to track the current position
2. How to loop through the steps
3. How to check if a number is a multiple of 5
4. The order of operations (check position THEN apply movement)

Good luck on your journey through the flatweed fields! 🌾✨
