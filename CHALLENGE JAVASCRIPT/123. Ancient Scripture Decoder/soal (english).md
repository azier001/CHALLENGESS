# 📜 Ancient Scripture Decoder

## Challenge Overview

**Difficulty Level:** `Easy` 🟢

Decode hidden messages by combining words from two ancient scripture lines!

---

## 🎯 Objective

Create a function named `decodeScripture` that reveals secret messages by merging words from two different lines of text.

### How It Works

The decoder extracts the **last two words** from an additional line and appends them to the original line, forming a complete decoded message.

---

## 📋 Function Specification

### Function Name
```
decodeScripture
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `originalLine` | `array of strings` | Words from the original scripture line |
| `additionalLine` | `array of strings` | Words from an additional line (last two words will be extracted) |

### Return Value

- **Type:** `array of strings`
- **Description:** The decoded message combining words from both lines

---

## 🔍 Decoding Process

1. **Start** with the `originalLine` array
2. **Extract** the last two words from `additionalLine`
3. **Append** those two words to `originalLine`
4. **Return** the combined array as the decoded message

---

## 💡 Example

```javascript
// Input
originalLine = ["The", "ancient", "wisdom"]
additionalLine = ["is", "hidden", "within", "the", "scrolls"]

// Process
// Last two words from additionalLine: ["the", "scrolls"]

// Output
decodeScripture(originalLine, additionalLine)
// Returns: ["The", "ancient", "wisdom", "the", "scrolls"]
```

---

## ✅ Requirements Checklist

- [ ] Function must be named `decodeScripture`
- [ ] Accept two parameters: `originalLine` and `additionalLine`
- [ ] Extract exactly the last **two words** from `additionalLine`
- [ ] Append extracted words to `originalLine`
- [ ] Return the result as an array of strings

---

## 🚀 Getting Started

Implement the function following the specifications above. Remember to handle edge cases and ensure your solution works with various input sizes!

**Good luck, decoder! 🔓**
