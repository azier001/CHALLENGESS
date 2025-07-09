# 🔍 Count Substring Occurrences Challenge

## 📊 Difficulty Level
**Easy**

## 🎯 Objective
Create a function named `countSubstringOccurrences` that analyzes string patterns and counts occurrences of specific substrings.

## 📝 Function Requirements

### Function Signature
```javascript
function countSubstringOccurrences(str, substr, maxLen)
```

### Parameters
- **`str`** (string): The main string to search within
- **`substr`** (string): The substring that must be included in results
- **`maxLen`** (number): Maximum length allowed for found substrings

### Return Value
- **Object**: Keys are found substrings, values are occurrence counts
- **Empty Object**: If `substr` is empty or `maxLen` is 0

## 🔧 Function Specifications

The function must:

1. **Find unique substrings** of `str` that meet ALL criteria:
   - ✅ Contains `substr` as a substring
   - ✅ Length ≤ `maxLen`
   - ✅ Contains no digits (0-9)

2. **Count occurrences** of each valid substring in the original string

3. **Return structured data** as an object with substring-count pairs

## 📋 Edge Cases

- If `substr` is an **empty string** → return `{}`
- If `maxLen` is **0** → return `{}`
- Substrings containing **digits** are excluded

## 💡 Example

### Input
```javascript
str = "abcabc"
substr = "ab"
maxLen = 4
```

### Output
```javascript
{
  "ab": 2,
  "abc": 2,
  "abca": 1,
  "abcab": 1
}
```

### Step-by-Step Breakdown

| Substring | Contains "ab"? | Length ≤ 4? | No Digits? | Count in "abcabc" |
|-----------|----------------|-------------|------------|-------------------|
| `"ab"`    | ✅ Yes         | ✅ Yes (2)  | ✅ Yes     | **2**             |
| `"abc"`   | ✅ Yes         | ✅ Yes (3)  | ✅ Yes     | **2**             |
| `"abca"`  | ✅ Yes         | ✅ Yes (4)  | ✅ Yes     | **1**             |
| `"abcab"` | ✅ Yes         | ✅ Yes (4)  | ✅ Yes     | **1**             |
| `"abcabc"`| ✅ Yes         | ❌ No (6)   | ✅ Yes     | **Excluded**      |

## 🎨 Key Considerations

- **Pattern Recognition**: Identify all possible substrings efficiently
- **String Matching**: Ensure `substr` is present in each result
- **Length Validation**: Respect the `maxLen` constraint
- **Character Filtering**: Exclude any substrings containing digits
- **Counting Logic**: Accurately count overlapping occurrences

## 🚀 Success Criteria

Your solution should:
- Handle all edge cases correctly
- Return accurate occurrence counts
- Maintain optimal performance
- Follow the exact function signature
- Pass all test scenarios

---

*Good luck with your implementation! 🎯*

