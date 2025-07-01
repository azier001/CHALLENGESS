# 🎯 Word Blend Adventure
## Challenge Level: **Easy** 🟢

---

## 📝 **Challenge Description**

Create a function named `blendWords` that intelligently combines two words by handling overlapping letters at their junction.

---

## 🎮 **Function Specification**

### **Function Name:** `blendWords`

### **Parameters:**
- `word1` (string) - The first word
- `word2` (string) - The second word

### **Returns:**
- `string` - The blended result of both words

---

## 🧩 **Logic Rules**

### **Rule 1: Duplicate Letter Handling**
> If the **last letter** of `word1` matches the **first letter** of `word2`, omit one duplicate

**Example:**
```
word1 = "hello"  (last letter: 'o')
word2 = "orange" (first letter: 'o')
Result: "hellorange" ✅
```

### **Rule 2: Empty String Handling**
> Return the non-empty string when one parameter is empty

**Examples:**
```
word1 = "hello", word2 = ""     → "hello"
word1 = "",      word2 = "world" → "world"
```

### **Rule 3: Both Empty**
> Return empty string when both parameters are empty

**Example:**
```
word1 = "", word2 = "" → ""
```

---

## 💡 **Test Cases**

| Input | Expected Output | Explanation |
|-------|-----------------|-------------|
| `("cat", "tiger")` | `"cattiger"` | No overlap |
| `("sun", "noon")` | `"sunnoon"` | 'n' overlap removed |
| `("hello", "")` | `"hello"` | Second word empty |
| `("", "world")` | `"world"` | First word empty |
| `("", "")` | `""` | Both empty |
| `("programming", "genius")` | `"programminggenius"` | 'g' overlap removed |

---

## 🚀 **Implementation Hints**

1. **Check for empty strings first**
2. **Compare last character of word1 with first character of word2**
3. **Use string slicing/substring methods for overlap removal**
4. **Concatenate appropriately based on conditions**

---

## 🎨 **Visual Flow**

```
Input: word1 = "hello", word2 = "orange"
                    ↓
              Check if empty?
                    ↓
         word1[-1] == word2[0] ?
              'o' == 'o' ✅
                    ↓
         Remove one duplicate
                    ↓
    "hello" + "range" = "hellorange"
```

---

## ✨ **Success Criteria**

- ✅ Function handles all edge cases correctly
- ✅ Proper duplicate letter removal logic
- ✅ Clean string concatenation
- ✅ Efficient and readable code

---

**Happy Coding! 🎉**
