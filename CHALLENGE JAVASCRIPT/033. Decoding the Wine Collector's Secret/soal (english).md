# 🍷 Decoding the Wine Collector's Secret

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that decodes a wine collector's encrypted secret message. This challenge combines string manipulation, binary conversion, and ASCII decoding to reveal hidden messages.

---

## 🎯 Objective

Implement a function named `decodeWineCollectorSecret` that processes a mixed-format encoded message containing:
- **Reversed words** (need to be flipped back)
- **Binary numbers** prefixed with `#` (need conversion to ASCII characters)

---

## 🔧 Function Specification

### Function Signature
```javascript
function decodeWineCollectorSecret(text)
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `text` | `string` | Input string containing reversed words and binary-coded numbers prefixed with "#" |

### Return Value
- **Type:** `string`
- **Description:** The fully decoded message

---

## 📖 Decoding Algorithm

The decoding process follows these steps:

1. **🔄 Reverse Words**: Identify and reverse any reversed words in the message
2. **🔢 Binary to Decimal**: Convert binary numbers (prefixed with `#`) to decimal format
3. **📝 Decimal to ASCII**: Transform decimal numbers into their corresponding ASCII characters

---

## 💡 Example

### Input
```
"yenw yessalm #01001000 #01100101 #01101100 #01101100 #01101111"
```

### Processing Steps
1. **Reverse words:**
   - `yenw` → `wine`
   - `yessalm` → `malmsey`

2. **Convert binary to decimal:**
   - `#01001000` → `72`
   - `#01100101` → `101`
   - `#01101100` → `108`
   - `#01101100` → `108`
   - `#01101111` → `111`

3. **Convert decimal to ASCII:**
   - `72` → `H`
   - `101` → `e`
   - `108` → `l`
   - `108` → `l`
   - `111` → `o`

### Output
```
"wine malmsey Hello"
```

---

## 🎨 Implementation Tips

- Split the input string to process individual tokens
- Use string reversal methods for reversed words
- Implement binary-to-decimal conversion for `#` prefixed tokens
- Use ASCII conversion functions to get characters from decimal values
- Join all processed elements with spaces

---

## 🏆 Success Criteria

Your function should successfully:
- ✅ Identify and reverse all reversed words
- ✅ Detect binary numbers with `#` prefix
- ✅ Convert binary to decimal correctly
- ✅ Transform decimal to ASCII characters
- ✅ Return the complete decoded message as a string

---

## 🔍 Edge Cases to Consider

- Empty input strings
- Strings with only reversed words
- Strings with only binary numbers
- Mixed case scenarios
- Invalid binary formats

---

*Good luck decoding the wine collector's secrets! 🍾*
