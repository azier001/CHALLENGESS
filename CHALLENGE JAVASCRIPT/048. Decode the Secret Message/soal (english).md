# 🔐 Decode Secret Message Challenge

> **Difficulty Level:** `Easy`  
> **Category:** Cryptography & String Manipulation

---

## 📋 Challenge Overview

As a **cryptography expert**, you've intercepted an encoded message and have access to a codebook. Your mission is to decode the message using a specific algorithm that involves reversing, splitting, and validating against a codebook.

---

## 🎯 Function Specification

### Function Signature
```javascript
function decodeSecretMessage(encodedMessage, codebook)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `encodedMessage` | `string` | The encoded message to be decoded |
| `codebook` | `string[]` | An array of strings representing the codebook |

### Return Value
- **Type:** `string`
- **Description:** The decoded message with unauthorized words replaced by "REDACTED"

---

## 🔧 Decoding Algorithm

Follow these **6 sequential steps** to decode the message:

### Step 1: Reverse the Message
```
Original: "dlrow olleh"
Reversed: "hello world"
```

### Step 2: Split into Words
```
Input: "hello world"
Output: ["hello", "world"]
```

### Step 3-4: Validate Against Codebook
For each word in the split message:
- ✅ **If found in codebook** → Keep the word as is
- ❌ **If NOT found in codebook** → Replace with `"REDACTED"`

### Step 5: Join Words
```
Processed words: ["hello", "REDACTED"]
Result: "hello REDACTED"
```

### Step 6: Return Result
Return the final decoded string.

---

## 📝 Important Notes

> ⚠️ **Punctuation Handling**  
> The encoded message may contain punctuation marks. Treat words separated by spaces as individual words, **regardless of punctuation**.

### Examples of Word Separation:
- `"hello, world!"` → `["hello,", "world!"]`
- `"test-case"` → `["test-case"]` (single word)
- `"a b c"` → `["a", "b", "c"]`

---

## 🧪 Example Walkthrough

Let's trace through a complete example:

```javascript
// Input
encodedMessage = "!dlrow ,olleh"
codebook = ["hello,", "world"]

// Step 1: Reverse
// "!dlrow ,olleh" → "hello, world!"

// Step 2: Split
// ["hello,", "world!"]

// Step 3-4: Check codebook
// "hello," ✅ (found in codebook)
// "world!" ❌ (not found in codebook) → "REDACTED"

// Step 5-6: Join and return
// Result: "hello, REDACTED"
```

---

## 🚀 Implementation Tips

- Use built-in string methods for reversing and splitting
- Consider using array methods for efficient codebook lookups
- Remember to handle edge cases (empty strings, single words, etc.)
- Test with various punctuation scenarios

---

## 📊 Complexity Analysis

- **Time Complexity:** O(n + m×k) where n = message length, m = number of words, k = codebook size
- **Space Complexity:** O(n) for storing the reversed and split message

---

*Happy coding! 🎉*
