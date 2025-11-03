# 🧺 Picnic Park Geometry Challenge

> **Difficulty Level:** `Hard` 🔴

---

## 📋 Challenge Overview

Create a function named **`arrangePicnic`** that arranges picnic items (represented as geometric shapes) on a 2D grid. The function applies a specified transformation to each item and detects any overlaps between them.

---

## 🎯 Function Signature

```javascript
function arrangePicnic(items, transformation)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `items` | `string[]` | An array of strings representing picnic items and their dimensions |
| `transformation` | `string` | A string specifying the transformation to be applied to all items |

### Returns

- **Type:** `boolean[]`
- **Description:** An array indicating whether each item overlaps with any other item after the transformation
- `true` = item overlaps with at least one other item
- `false` = item does not overlap with any other item

---

## 🔷 Supported Shapes

The function supports three geometric shapes, each with specific dimension parameters:

### 1. **Triangle**
```
Format: "triangle,side1,side2,side3"
Example: "triangle,3,4,5"
```
- Requires three side lengths

### 2. **Circle**
```
Format: "circle,radius"
Example: "circle,5"
```
- Requires one radius value

### 3. **Rectangle**
```
Format: "rectangle,width,height"
Example: "rectangle,4,6"
```
- Requires width and height dimensions

---

## 🔄 Supported Transformations

The function supports two types of geometric transformations:

### 1. **Rotation**
```
Format: "rotate,degrees"
Example: "rotate,90"
```
- Rotates the shape by the specified angle (in degrees)

### 2. **Scaling**
```
Format: "scale,factor"
Example: "scale,2"
```
- Scales the shape by the specified factor (multiplies dimensions)

---

## ⚙️ Implementation Steps

1. **Parse Item Strings**
   - Extract shape type and dimensions from each item string
   - Validate the shape format and parameters

2. **Apply Transformation**
   - Apply the specified transformation to each parsed item
   - Update coordinates and dimensions accordingly

3. **Detect Overlaps**
   - Compare transformed coordinates and dimensions of all items
   - Determine which items overlap with each other

4. **Return Results**
   - Generate a boolean array indicating overlap status for each item

---

## 💡 Example Usage

```javascript
const items = [
  "triangle,3,4,5",
  "circle,5",
  "rectangle,4,6"
];

const transformation = "scale,2";

const result = arrangePicnic(items, transformation);
// Returns: [boolean, boolean, boolean]
```

---

## 🎓 Key Considerations

- ⚠️ Ensure proper parsing of item strings
- 🔍 Accurate geometric calculations for overlap detection
- 📐 Correct application of transformations (rotation/scaling)
- 🔢 Handle edge cases (invalid inputs, zero dimensions, etc.)
- 🎯 Efficient algorithm for comparing multiple items

---

## 🏆 Success Criteria

Your implementation should:

✅ Correctly parse all supported shape formats  
✅ Apply transformations accurately  
✅ Detect overlaps between any combination of shapes  
✅ Return the correct boolean array  
✅ Handle edge cases gracefully  

---

Good luck with your implementation! 🚀
