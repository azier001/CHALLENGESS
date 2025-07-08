# 🏚️ Haunted House Message Transformer

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Create a function that transforms ordinary messages into spine-chilling communications, as if discovered in the depths of a haunted mansion. This challenge draws inspiration from a couple's eerie anniversary adventure in an old, mysterious house where cryptic messages await decoding.

---

## 🎯 Objective

Develop a function named `createSpookyMessage` that takes a regular message and transforms it into a haunting communication by reversing word order and replacing specific words with their sinister counterparts.

---

## 📝 Function Requirements

### Function Signature
```javascript
function createSpookyMessage(message)
```

### Parameters
- **`message`** *(string)*: The original message discovered in the haunted house

### Return Value
- **Returns**: A string representing the transformed spooky message

---

## 🔧 Implementation Steps

Follow these sequential steps to create the spooky transformation:

1. **Split the Message**
   - Break the input string into individual words

2. **Reverse Word Order**
   - Rearrange the words in reverse sequence

3. **Apply Spooky Replacements**
   - Transform specific words using the haunted dictionary below

4. **Reconstruct the Message**
   - Join the modified words back into a single string

---

## 👻 Spooky Word Dictionary

Replace the following words with their eerie alternatives:

| Original Word | Spooky Replacement |
|---------------|-------------------|
| `"happy"`     | `"haunted"`       |
| `"love"`      | `"fear"`          |
| `"together"`  | `"trapped"`       |
| `"forever"`   | `"nevermore"`     |

---

## 🏠 Story Context

*On their wedding anniversary, a couple decides to explore an old, abandoned house rumored to be haunted. As they venture deeper into the mansion, they discover mysterious messages carved into the walls and written on dusty papers. These messages seem to be encoded in a peculiar way - the words are jumbled and certain phrases have been replaced with more sinister alternatives. Your task is to create a decoder that can transform these spooky messages back to their original form... or perhaps transform innocent messages into haunting warnings.*

---

## 💡 Example Usage

```javascript
// Example input
const originalMessage = "We will be happy together forever in love";

// Expected transformation process:
// 1. Split: ["We", "will", "be", "happy", "together", "forever", "in", "love"]
// 2. Reverse: ["love", "in", "forever", "together", "be", "happy", "will", "We"]
// 3. Replace: ["fear", "in", "nevermore", "trapped", "be", "haunted", "will", "We"]
// 4. Join: "fear in nevermore trapped be haunted will We"

const spookyMessage = createSpookyMessage(originalMessage);
console.log(spookyMessage); // Output: "fear in nevermore trapped be haunted will We"
```

---

## 🎃 Challenge Notes

- The function should handle any input string
- Word matching for replacements should be case-sensitive
- Maintain original spacing between words in the final output
- The transformation creates an eerie, backwards narrative perfect for Halloween atmospheres

---

*Good luck decoding the mysteries of the haunted house! 👻*
