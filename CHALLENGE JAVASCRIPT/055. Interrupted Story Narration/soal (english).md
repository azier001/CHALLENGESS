# 🔍 Interrupted Story Narration Challenge

## 📊 Difficulty Level
**Easy**

---

## 🎯 Objective

Create a function named `findStopWord` that processes an array of sentences and returns a subset based on a specified stop word condition.

## 📝 Function Specification

### Function Name
```javascript
findStopWord(sentences, stopWord)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `sentences` | `array` | An array of strings where each string represents a sentence from the story |
| `stopWord` | `string` | The keyword that triggers the story narration to stop |

### Return Value
- **Type**: `array`
- **Content**: Array of strings containing sentences from the start until the `stopWord` is encountered for the first time
- **Special Case**: If `stopWord` is not found, returns the original `sentences` array

---

## 🔧 Implementation Requirements

### Core Logic
1. **Loop through** the given array of sentences
2. **Check each sentence** for the presence of the `stopWord`
3. **Terminate immediately** when `stopWord` is found using the `break` statement
4. **Return array** containing all sentences up to and including the sentence with the `stopWord`

### Key Points
- ✅ Include the sentence containing the `stopWord` in the result
- ✅ Use `break` statement for immediate loop termination
- ✅ Handle case where `stopWord` is not found (return entire array)
- ✅ Process sentences sequentially from beginning

---

## 💡 Expected Behavior

### Scenario 1: Stop Word Found
```
Input: ["Once upon a time", "There was a dragon", "The end came quickly"]
Stop Word: "dragon"
Output: ["Once upon a time", "There was a dragon"]
```

### Scenario 2: Stop Word Not Found
```
Input: ["Once upon a time", "There was a princess", "She lived happily"]
Stop Word: "dragon"
Output: ["Once upon a time", "There was a princess", "She lived happily"]
```

---

## 🏷️ Tags
`Array Processing` • `String Manipulation` • `Loop Control` • `Conditional Logic`
