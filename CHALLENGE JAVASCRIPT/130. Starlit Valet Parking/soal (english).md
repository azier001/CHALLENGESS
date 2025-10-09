# 🌟 Starlit Valet Parking

## Challenge Level
**Easy** ⭐

---

## 📖 Story

As the valet at a quaint countryside inn on a starlit night, you need to arrange the arriving cars in the parking lot. Your task is to create a **zigzag pattern** that mimics the twinkling of stars in the night sky.

---

## 🎯 Objective

Create a function named `parkingValet` that arranges cars in rows, alternating between **forward** and **reverse** order for each row. If there are not enough cars to fill a row, use dashes (`'-'`) to represent empty spots.

---

## 📋 Function Specification

### Function Name
```
parkingValet
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `licensePlates` | `string` | A string of uppercase letters, each representing a car's license plate |
| `spotsPerRow` | `number` | The number of parking spots in each row of the lot |

### Return Value

- **Type:** `Array<Array<string>>`
- **Description:** A 2D array of strings, where each inner array represents a row in the parking lot

---

## 🔍 Requirements

1. ✅ Arrange cars in rows based on `spotsPerRow`
2. ✅ Alternate between forward and reverse order for each row (zigzag pattern)
3. ✅ Fill incomplete rows with dashes (`'-'`)
4. ✅ Each license plate is represented by a single uppercase letter

---

## 💡 Example

```javascript
// Input
licensePlates: "ABCDEFGH"
spotsPerRow: 3

// Output
[
  ['A', 'B', 'C'],
  ['F', 'E', 'D'],
  ['G', 'H', '-']
]
```

### Visual Representation

```
Row 1 (Forward):  A → B → C
Row 2 (Reverse):  F ← E ← D
Row 3 (Forward):  G → H → -
```

The pattern creates a zigzag effect like stars twinkling across the night sky! ✨

---

## 🎨 Pattern Explanation

- **Row 1:** Forward order (left to right)
- **Row 2:** Reverse order (right to left)
- **Row 3:** Forward order (left to right)
- **Row 4:** Reverse order (right to left)
- And so on...

---

## 📝 Notes

- Empty spots should be represented by the dash character: `'-'`
- Each license plate is a single uppercase letter
- The zigzag pattern alternates with each new row

---

**Happy Coding!** 🚗💨
