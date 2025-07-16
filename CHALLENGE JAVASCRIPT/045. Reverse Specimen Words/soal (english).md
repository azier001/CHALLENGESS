# 🔬 Reverse Specimen Words Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

As a curious entomologist examining a stricken insect specimen with a nibbed pen, you've decided to encode your observations by reversing the letters in each word. Your task is to create a function that takes a sentence about an insect observation and returns a new sentence where each word's letters are reversed, while maintaining the original word order.

---

## 🎯 Objective

Create a function named `reverseSpecimenWords` that receives `observation` as its parameter and returns an encoded version of the observation.

---

## 📝 Function Specification

### Function Name
```javascript
reverseSpecimenWords(observation)
```

### Parameters
- **`observation`** *(string)*: A sentence describing an insect observation
  - May contain letters, numbers, and basic punctuation
  - Words are separated by spaces

### Return Value
- **Type:** `string`
- **Description:** A new sentence where each word's letters are reversed, but the words remain in the same order

---

## 🔧 Implementation Strategy

Follow this step-by-step approach to solve the problem:

1. **Split the input string** into an array of words
2. **Create a new array** where each word is reversed
3. **Join the array** of reversed words back into a single string

### 💡 Important Notes

> **Punctuation Handling:** Punctuation should remain in its original position relative to the word it's attached to.

> **Space Preservation:** Maintain proper spacing between words in the output.

---

## 📚 Example Usage

```javascript
// Example function call
const observation = "The beetle crawls slowly.";
const encoded = reverseSpecimenWords(observation);
console.log(encoded); // Expected output: "ehT elteeb slwarc ylwols."
```

---

## ✅ Testing Scenarios

Consider testing your function with these types of inputs:

- **Simple words:** `"ant bee"`
- **Words with punctuation:** `"Hello, world!"`
- **Mixed content:** `"The spider has 8 legs."`
- **Single word:** `"butterfly"`
- **Empty string:** `""`

---

## 🐛 Edge Cases to Consider

- Words containing numbers
- Multiple spaces between words
- Punctuation at the beginning or end of words
- Special characters and symbols

---

*Happy coding, fellow entomologist! 🦗*
