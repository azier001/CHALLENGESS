# Artistic Sign Creation Challenge

## 🎯 Difficulty Level
**Easy**

## 📝 Description
Create a function named `createArtisticSign` that receives `text` and `decorations` as its parameters.

This function aims to create a beautifully decorated sign by combining the provided text with the specified decorations.

## 🎨 Concept
- The `text` parameter represents the main message that will be inscribed on the sign
- Imagine the text written in a gorgeous cursive font
- The `decorations` parameter contains decorative elements that enhance the sign's appearance

## 🔧 Parameters

### `text` (string)
- The main message to be inscribed on the sign
- This will be the central content of your artistic sign

### `decorations` (string)
- A string containing only two types of characters: `&` and `*`
- **`&` character**: Represents a lovely vine decoration
  - Should be placed **before** the text
- **`*` character**: Represents a charming knot decoration
  - Should be placed **after** the text

## 📋 Requirements
Your task is to create a function that:
1. Takes the two parameters (`text` and `decorations`)
2. Returns a beautifully decorated sign text
3. Places vine decorations (`&`) on the left side of the text
4. Places knot decorations (`*`) on the right side of the text

## 🎯 Expected Output
The function should return a string representing the final decorated sign, with:
- Text surrounded by vine decorations (`&`) on the left
- Text surrounded by knot decorations (`*`) on the right

## 💡 Example
```javascript
// Example usage:
createArtisticSign("Welcome", "&&**")
// Expected output: "&&Welcome**"

createArtisticSign("Hello World", "&*&*")
// Expected output: "&&Hello World**"
```

## 🚀 Implementation Tips
1. Separate the vine (`&`) and knot (`*`) characters from the decorations string
2. Concatenate vine decorations + text + knot decorations
3. Return the final decorated string
