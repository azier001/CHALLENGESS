# 🎯 Inmate Profile Sketch Challenge

## 📋 Challenge Overview

| **Difficulty** | **Easy** |
|----------------|----------|
| **Function Name** | `sketchInmateProfile` |
| **Return Type** | String |

---

## 📝 Problem Description

Create a function to help a prison guard create a simple ASCII sketch of an inmate's side profile. The guard needs to arrange the facial features correctly based on which direction the inmate is facing.

---

## 🔧 Function Signature

```javascript
function sketchInmateProfile(features, facingLeft) {
    // Your implementation here
}
```

---

## 📥 Parameters

### `features` (Array)
- **Type**: Array of strings
- **Description**: Each string is a single character representing a facial feature
- **Example**: `['|', 'O', ')', '-', '>']`

### `facingLeft` (Boolean)
- **Type**: Boolean
- **Description**: Indicates the direction the inmate is facing
- **Values**: 
  - `true` = facing left
  - `false` = facing right

---

## 🎯 Requirements

The function should return a **single string** that represents the sketched profile of the inmate.

---

## 📐 Algorithm Steps

Follow these steps to create the sketch:

### Step 1: Check Direction
```
IF facingLeft is true:
    Reverse the order of the features array
```

### Step 2: Join Characters
```
Join all characters in the features array into a single string
```

### Step 3: Swap Direction Characters
```
IF facingLeft is true:
    Replace '<' with '>' and '>' with '<' in the resulting string
```

---

## ⚠️ Important Notes

> **Note**: The sketch should always be a **single line**, with **no spaces** between the characters.

---

## 💡 Example Usage

```javascript
// Example 1: Facing Right
const features1 = ['|', 'O', ')', '-', '>'];
const result1 = sketchInmateProfile(features1, false);
// Expected output: "|O)->"

// Example 2: Facing Left
const features2 = ['|', 'O', ')', '-', '>'];
const result2 = sketchInmateProfile(features2, true);
// Expected output: "<-)|O"
```

---

## 🔍 Key Points to Remember

- ✅ Always return a single string
- ✅ No spaces between characters
- ✅ Reverse array order when facing left
- ✅ Swap '<' and '>' characters when facing left
- ✅ Process steps in the correct order

---

## 🚀 Getting Started

1. Create the function with the specified name and parameters
2. Implement the logic following the three steps outlined above
3. Test with different feature arrays and directions
4. Ensure the output matches the expected format

---

*Good luck with your implementation! 🎉*
