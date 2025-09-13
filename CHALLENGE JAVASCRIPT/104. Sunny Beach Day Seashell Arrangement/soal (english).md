# 🏖️ Sunny Beach Day Seashell Arrangement

## 🌟 Challenge Overview

**Difficulty Level:** `Easy` 🟢

Create a function named `sunnyBeachDay` that transforms a collection of seashells based on the sun's position and beach day magic!

## 🎯 The Scenario

Picture yourself enjoying a perfect sunny day at the beach, carefully arranging beautiful seashells on your colorful beach towel. As the sun moves across the sky, it affects your seashell collection in mysterious ways, and you need to rearrange them following nature's rules.

## 📋 Function Specification

### Function Signature
```javascript
function sunnyBeachDay(seashells, sunPosition)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `seashells` | `Array<number>` | An array of integers (1-5) representing different seashell types |
| `sunPosition` | `number` | Index where the sun shines brightest (0 ≤ sunPosition < seashells.length) |

### Return Value
- **Type:** `Array<number>`
- **Description:** The rearranged seashells after applying all transformation rules

## 🔄 Transformation Rules

Follow these steps in order to create your perfect beach arrangement:

### 1. ↩️ Reverse by Sun Position
- **Left Side:** Reverse all seashells to the **left** of the sun position
- **Right Side:** Reverse all seashells to the **right** of the sun position
- **Sun Position:** The seashell at sun position remains unchanged initially

### 2. ☀️ Sun Bleaching Effect
- Replace any **type 3** seashells with **type 2** seashells
- *Reason:* The intense sunlight bleaches type 3 shells, transforming them

### 3. ✨ Premium Placement
- Move all **type 5** seashells to the **beginning** of the array
- *Reason:* These are the prettiest shells and deserve the top spot on your towel
- Maintain their relative order when moving

## 💡 Example Walkthrough

```
Initial: [1, 3, 2, 4, 5]  sunPosition: 2
Step 1:  [3, 1, 2, 4, 5]  (reverse left: [1,3] → [3,1], reverse right: [4,5] → [5,4])
Step 2:  [2, 1, 2, 5, 4]  (replace 3→2)
Step 3:  [5, 2, 1, 2, 4]  (move type 5 to front)
```

## 🏁 Expected Output

Your function should return a beautifully arranged array that represents the final seashell layout on your beach towel, following all the sun-kissed transformation rules.

---

*Happy coding, and enjoy your virtual beach day! 🌊🐚*
