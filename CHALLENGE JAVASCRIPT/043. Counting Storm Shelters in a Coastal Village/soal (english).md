# 🌊 Counting Storm Shelters in a Coastal Village

## 🎯 Challenge Overview
**Difficulty:** `Easy`

In a coastal village, ancient stone walls stand against fierce storms. Your task is to identify the number of **storm shelters** among these walls. A storm shelter is a wall that is taller than all the walls to its right, providing crucial protection for villagers during severe weather.

## 📋 Problem Description

Create a function named `findStormShelters` that identifies walls serving as storm shelters by:
- Iterating through the array from **right to left**
- Keeping track of the maximum height seen so far
- Counting walls that exceed this maximum

## 🔧 Function Specification

### Function Signature
```javascript
function findStormShelters(wallHeights)
```

### Parameters
- **`wallHeights`** *(array)*: An array of numbers representing the heights of the stone walls
  - Each number is a positive integer
  - Represents wall heights from left to right

### Return Value
- **Number**: The count of storm shelters (walls taller than all walls to their right)

## 📊 Examples

### Example 1
```javascript
findStormShelters([3, 7, 8, 3, 6, 1])
// Returns: 3
```
**Explanation:** Storm shelters are at indices 2, 1, and 0 (heights 8, 7, and 3 respectively)

### Example 2
```javascript
findStormShelters([5, 4, 3, 2, 1])
// Returns: 5
```
**Explanation:** All walls are storm shelters since each is taller than all walls to its right

### Example 3
```javascript
findStormShelters([1, 2, 3, 4, 5])
// Returns: 1
```
**Explanation:** Only the rightmost wall (height 5) is a storm shelter

## 🧠 Algorithm Approach

1. **Start from the rightmost wall** and move left
2. **Track the maximum height** encountered so far
3. **Count walls** that are taller than the current maximum
4. **Update the maximum** when a taller wall is found

## 💡 Key Insights

- The rightmost wall is always a storm shelter
- A wall qualifies as a storm shelter if it's taller than all walls to its right
- Processing from right to left allows efficient tracking of the maximum height
- Time complexity: O(n) - single pass through the array
- Space complexity: O(1) - only need to track maximum height and count

## 🎨 Visual Representation

For array `[3, 7, 8, 3, 6, 1]`:

```
Height
  8 |   █
  7 | █ █
  6 | █ █   █
  5 | █ █   █
  4 | █ █   █
  3 | █ █ █ █
  2 | █ █ █ █
  1 | █ █ █ █ █ █
    +-------------
      3 7 8 3 6 1
      ↑ ↑ ↑     
    Storm Shelters
```

The walls at positions 0, 1, and 2 (heights 3, 7, and 8) are storm shelters because each is taller than all walls to its right.
