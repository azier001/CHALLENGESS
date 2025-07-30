# 🌼 Arranging Daffodils by Height

## 🎯 Challenge Overview
**Difficulty Level:** `Easy`

On a sunny spring morning, a gardener is tending to a row of beautiful daffodils. To create a perfectly neat arrangement, the gardener needs to sort the daffodils based on their heights. Your mission is to help the gardener organize these flower measurements in ascending order.

---

## 📋 Task Description

Create a function named **`arrangeDaffodils`** that will help sort daffodil heights from shortest to tallest.

### Function Signature
```javascript
function arrangeDaffodils(daffodilHeights) {
    // Your implementation here
}
```

---

## 🔧 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `daffodilHeights` | `Array<number>` | An array of integers representing the heights of daffodils in centimeters |

---

## 📤 Return Value

- **Type:** `Array<number>`
- **Description:** An array of integers representing the sorted heights of the daffodils in ascending order (shortest to tallest)

---

## 💡 Example

### Input:
```javascript
daffodilHeights = [15, 8, 23, 12, 19, 6, 21]
```

### Expected Output:
```javascript
[6, 8, 12, 15, 19, 21, 23]
```

### Visual Representation:
```
Before: 🌼15  🌼8   🌼23  🌼12  🌼19  🌼6   🌼21
After:  🌼6   🌼8   🌼12  🌼15  🌼19  🌼21  🌼23
```

---

## ✅ Requirements

- ✨ Sort the array in **ascending order** (shortest to tallest)
- 🔄 Return the sorted array
- 📏 Heights are measured in centimeters
- 🌱 Handle arrays of any length (including empty arrays)

---

## 🌟 Tips

> 💭 **Think about:** What built-in JavaScript methods can help you sort an array of numbers?
> 
> ⚠️ **Remember:** JavaScript's default sort method treats elements as strings, so be careful when sorting numbers!

---

*Happy coding! 🌼✨*
