# 🚂 Train's Journey Through the Night

## 📋 Challenge Overview

**Difficulty Level:** `Easy`  
**Challenge Type:** String Manipulation

---

## 🎯 Objective

Create a function named `trainJourney` that simulates a train's magical journey through the night by transforming an input string through a series of specific operations.

---

## 📝 Function Specification

### Function Signature
```javascript
function trainJourney(string)
```

### Parameters
- **Input:** `string` - The original string representing the train's route

### Return Value
- **Output:** `string` - The transformed string representing the completed night journey

---

## 🔧 Transformation Steps

The function must perform the following operations **in order**:

### Step 1: 🔄 Reverse Word Order
Reverse the order of words in the input string while maintaining the words themselves intact.

### Step 2: 🔤 Capitalize Every 3rd Character
Starting from the **first character** (index 0), capitalize every 3rd character in the reversed string.
- Characters at positions: 0, 3, 6, 9, 12, ... should be capitalized

### Step 3: 🚂 Add Train Sound
Concatenate the string `" choo choo!"` to the end of the modified string.

---

## 💡 Example Walkthrough

```
Input: "hello world night"

Step 1 - Reverse words:
"night world hello"

Step 2 - Capitalize every 3rd character (positions 0, 3, 6, 9, 12...):
"NigHt World hEllo"
 ↑  ↑     ↑   ↑

Step 3 - Add train sound:
"NigHt World hEllo choo choo!"

Final Output: "NigHt World hEllo choo choo!"
```

---

## ✅ Requirements Checklist

- [ ] Function is named `trainJourney`
- [ ] Accepts a single string parameter
- [ ] Returns a string
- [ ] Correctly reverses word order
- [ ] Capitalizes every 3rd character starting from index 0
- [ ] Appends `" choo choo!"` to the result
- [ ] Handles edge cases (empty strings, single words, etc.)

---

## 🚀 Implementation Tips

> **Hint:** Consider breaking down the problem into smaller functions for each transformation step to make your code more readable and maintainable.

> **Note:** Remember that string indexing starts at 0, so the "first character" for capitalization is at index 0.

---

## 🧪 Testing Your Solution

Make sure to test your function with various inputs:
- Single words
- Multiple words
- Empty strings
- Strings with special characters
- Long sentences

Happy coding! 🎉
