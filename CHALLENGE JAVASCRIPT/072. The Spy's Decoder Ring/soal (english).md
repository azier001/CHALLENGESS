# 🕵️ The Spy's Decoder Ring

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that decodes secret binary messages using a substitution cipher. Perfect your skills in binary manipulation and string processing while uncovering hidden messages!

---

## 🎯 Objective

Implement a function named `decodeMessage` that converts binary-encoded messages back into readable text using alphabet-to-number mapping.

### Function Signature
```javascript
function decodeMessage(binaryMessage) {
    // Your implementation here
}
```

---

## 🔧 How It Works

The decoding process follows a specific substitution cipher where:
- Each letter corresponds to its position in the alphabet
- Letters are encoded as binary numbers
- Spaces have a special binary representation

### Encoding Reference
| Letter | Decimal Value | Binary Equivalent |
|--------|---------------|-------------------|
| A      | 1             | `1`               |
| B      | 2             | `10`              |
| C      | 3             | `11`              |
| ...    | ...           | ...               |
| Z      | 26            | `11010`           |
| Space  | 32            | `00100000`        |

---

## 📝 Decoding Steps

Follow these steps to decode the binary message:

1. **🔍 Split the Message**
   - Separate the binary message into individual binary numbers
   - Each number represents either a letter or a space

2. **🔢 Binary to Decimal Conversion**
   - Convert each binary number to its decimal equivalent
   - Use standard binary-to-decimal conversion methods

3. **📚 Alphabet Mapping**
   - Map decimal values to corresponding alphabet letters
   - Use the formula: `1 = A, 2 = B, ..., 26 = Z`
   - Handle spaces with decimal value `32`

4. **🔗 Concatenate Results**
   - Join all decoded letters to form the final message
   - Preserve spaces for proper word separation

---

## 💡 Special Cases

### Space Character
- **Binary Representation:** `00100000`
- **Decimal Value:** `32`
- **Output:** Single space character ` `

---

## 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `binaryMessage` | `string` | The binary encoded message to be decoded |

---

## 📤 Return Value

| Type | Description |
|------|-------------|
| `string` | The decoded message in readable text format |

---

## 🧪 Example Usage

```javascript
// Example binary input (represents "HELLO WORLD")
const binaryInput = "1000 101 1100 1100 1111 00100000 10111 1111 10010 1100 100";

const result = decodeMessage(binaryInput);
console.log(result); // Expected output: "HELLO WORLD"
```

---

## ✅ Success Criteria

Your solution should:
- ✅ Handle all letters A-Z correctly
- ✅ Process spaces properly
- ✅ Return the complete decoded message
- ✅ Work with any valid binary input format

---

## 🚀 Ready to Start?

Put on your decoder hat and start cracking those binary messages! Remember to test your function with various inputs to ensure it works correctly with different message lengths and content.

Good luck, Agent! 🎯
