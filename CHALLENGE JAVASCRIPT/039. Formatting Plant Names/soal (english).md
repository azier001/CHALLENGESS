# 🌱 Plant Name Formatter Challenge

## 📋 Challenge Overview

**Difficulty:** `Easy`  
**Function Name:** `formatPlantName`

Create a function that properly formats plant names by capitalizing the first letter of each word while making all other letters lowercase.

## 🎯 Objective

Transform plant names from various formats (all lowercase, all uppercase, or mixed case) into a standardized format with proper capitalization.

## 📝 Function Specification

### Parameters
- **`plantName`** *(string)*: The name of the plant that needs formatting
  - May be in all lowercase, all uppercase, or mixed case
  - Contains one or more words separated by spaces

### Returns
- **`string`**: The formatted plant name with proper capitalization

## 🔧 Implementation Steps

Follow these steps to solve the challenge:

1. **Split the string** 
   - Use `split()` to convert the `plantName` string into an array of words

2. **Process each word**
   - Loop through each word in the array
   - Apply proper capitalization to each word

3. **Capitalize properly**
   - Use `toUpperCase()` for the first letter
   - Use `toLowerCase()` for the remaining letters

4. **Reconstruct the string**
   - Use `join()` with a space as separator to combine words back into a single string

5. **Return the result**
   - Return the formatted plant name

## 📊 Example Usage

```javascript
// Example inputs and expected outputs
formatPlantName("rose bush") → "Rose Bush"
formatPlantName("SUNFLOWER") → "Sunflower"
formatPlantName("bAmBoO tReE") → "Bamboo Tree"
formatPlantName("african violet") → "African Violet"
```

## 🎨 Expected Behavior

| Input | Output |
|-------|---------|
| `"rose bush"` | `"Rose Bush"` |
| `"SUNFLOWER"` | `"Sunflower"` |
| `"bAmBoO tReE"` | `"Bamboo Tree"` |
| `"african violet"` | `"African Violet"` |

## 💡 Tips

- Remember to handle single-word plant names as well as multi-word names
- Consider edge cases like empty strings or strings with extra spaces
- Test your function with various input formats to ensure it works correctly

## 🏆 Success Criteria

Your function should:
- ✅ Properly capitalize the first letter of each word
- ✅ Convert all other letters to lowercase
- ✅ Handle various input formats correctly
- ✅ Return a properly formatted string

---

*Happy coding! 🌿*
