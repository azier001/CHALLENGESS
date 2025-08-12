# 🔐 Decipher Encrypted Message Challenge

## 📋 Challenge Overview

**Difficulty Level:** `Easy`  
**Function Name:** `decipherMessage`

---

## 🎯 Objective

Create a function that deciphers an encrypted message using a cipher key array. The cipher key contains indices that determine the order in which characters should be extracted from the encrypted message.

## 📝 Function Specification

### Function Signature
```javascript
function decipherMessage(encryptedMessage, cipherKey)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `encryptedMessage` | `string` | The encrypted message to be deciphered |
| `cipherKey` | `array` | Array of indices indicating character extraction order |

### Return Value
- **Type:** `string`
- **Description:** The deciphered message

---

## 🔧 How It Works

1. **Extract characters** from the `encryptedMessage` based on the indices in `cipherKey`
2. **Move each character** to the beginning of the deciphered message
3. **Repeat the process** until all characters have been processed
4. **Return** the final deciphered message

### Visual Example
```
Encrypted Message: "hello"
Cipher Key:        [4, 0, 3, 1, 2]

Step 1: Extract index 4 ('o') → "o"
Step 2: Extract index 0 ('h') → "ho" 
Step 3: Extract index 3 ('l') → "lho"
Step 4: Extract index 1 ('e') → "elho"
Step 5: Extract index 2 ('l') → "lelho"

Result: "lelho"
```

---

## ⚠️ Important Constraints

> **Character Set**
> - The `encryptedMessage` contains **only lowercase letters**

> **Array Properties**
> - The `cipherKey` array contains **all indices** of the `encryptedMessage`
> - Indices are provided in **shuffled order**
> - The length of `cipherKey` **always matches** the length of `encryptedMessage`

---

## 💡 Implementation Tips

- Consider using array manipulation methods
- Track which characters have already been processed
- Think about the order of operations when building the result
- Remember that each character moves to the "beginning" of the current result

---

## 🧪 Test Cases

Consider testing with:
- Single character messages
- Messages with repeated characters  
- Different cipher key arrangements
- Edge cases with empty strings (if applicable)

---

*Good luck solving this cipher challenge! 🚀*
