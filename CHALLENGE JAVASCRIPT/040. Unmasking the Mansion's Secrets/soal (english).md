# 🏚️ Unmasking the Mansion's Secrets

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that decodes mysterious messages found within an old mansion by applying a special transformation technique.

---

## 🎯 Objective

Implement a function named `decodeMessage` that takes a message and decodes it using a specific algorithm involving string reversal and concatenation.

---

## 🔧 Function Specification

### Function Name
```
decodeMessage
```

### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `message` | `string` | The original message to be decoded |

### Return Value
- **Type:** `string`
- **Description:** The decoded message after transformation

---

## 📝 Implementation Steps

Follow these steps to solve the challenge:

1. **Reverse the Message**
   - Take the input `message` string
   - Reverse its character order

2. **Concatenate Strings**
   - Combine the reversed message with the original message
   - Order: `reversed_message + original_message`

3. **Return Result**
   - Return the final concatenated string

---

## 💡 Example

```javascript
// Example usage
decodeMessage("hello")
// Step 1: Reverse "hello" → "olleh"
// Step 2: Concatenate "olleh" + "hello" → "ollehhello"
// Returns: "ollehhello"
```

---

## 🏗️ Solution Template

```javascript
function decodeMessage(message) {
    // Step 1: Reverse the message
    
    // Step 2: Concatenate reversed + original
    
    // Step 3: Return the result
}
```

---

## ✅ Success Criteria

Your function should:
- ✓ Accept a string parameter named `message`
- ✓ Correctly reverse the input string
- ✓ Concatenate the reversed string with the original
- ✓ Return the properly formatted decoded message

---

## 🔍 Testing Your Solution

Make sure to test your function with various inputs:
- Single character strings
- Empty strings
- Strings with spaces
- Strings with special characters

---

*Good luck uncovering the mansion's hidden secrets! 🔓*
