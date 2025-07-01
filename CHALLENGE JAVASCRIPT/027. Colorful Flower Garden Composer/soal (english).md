# 🌸 Colorful Flower Garden Composer

## Challenge Level
**Easy**

---

## 📋 Overview

Create a function named `flowerGardenComposer` that receives `flowerNames` and `separator` as its parameters. This function aims to create a colorful string representation of a flower garden by concatenating flower names with their associated colors.

---

## 🎯 Requirements

The function should follow these steps:

1. **Define a color palette**: Create a list of colors: `["red", "yellow", "pink", "blue", "purple"]`
2. **Initialize result storage**: Create an empty string variable to store the final result
3. **Iterate through flowers**: Loop through each flower name in the `flowerNames` array
4. **Assign colors**: For each flower name, determine its associated color using the index modulo the number of colors
5. **Build the string**: Concatenate the color, a space, and the flower name to the result string
6. **Add separators**: If the current flower is not the last one, append the `separator` to the result string
7. **Return the result**: Return the final result string

---

## 📥 Parameters

| Parameter | Type | Description | Constraints |
|-----------|------|-------------|-------------|
| `flowerNames` | `array of strings` | An array containing the names of the flowers | Maximum 10 items |
| `separator` | `string` | A string representing the separator to be used between the colored flower names | Any string |

---

## 📤 Return Value

The function returns a **string** that represents the colorful flower garden, with each flower name preceded by its associated color and separated by the specified `separator`.

---

## 💡 Example

```javascript
// Input
flowerNames = ["rose", "tulip", "daisy", "sunflower"]
separator = " | "

// Expected Output
"red rose | yellow tulip | pink daisy | blue sunflower"
```

---

## 🔧 Function Signature

```javascript
function flowerGardenComposer(flowerNames, separator) {
    // Your implementation here
}
```
