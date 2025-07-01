# 🕵️‍♂️ Shropshire Notary's Quirky Stamp

## 💼 Challenge Overview

**Difficulty:** Easy

Welcome to the whimsical world of Shropshire's notary! This notary has a peculiar habit: their stamp reverses the text and surrounds it with a bold border of asterisks.

Your mission is to recreate this quirky stamp through code.

---

## 🧠 Task Description

Create a function called `notaryStampReverse` that simulates the stamping process.

### Function Signature

```javascript
function notaryStampReverse(textArray, borderWidth)
```

### Parameters

- `textArray` (`array`):  
  A 2D array of strings representing the original text to be stamped.  
  Each inner array contains strings to be **reversed** and **concatenated**.

- `borderWidth` (`number`):  
  A positive integer representing the **width of the border** (made of `*`) that surrounds the stamped text.

---

## 📝 Requirements

1. 🔄 **Reverse** each string in the 2D array.
2. 🔗 **Concatenate** the reversed strings within each row using a **single space**.
3. ✨ **Add a border** of asterisks around the resulting text block, using the specified `borderWidth`.
4. 🧾 **Return** the final stamped output as a **single string**, including line breaks and borders.

---

## 🧪 Example

### Input

```javascript
notaryStampReverse(
  [
    ["Hello", "World"],
    ["Shropshire", "Notary"]
  ],
  2
);
```

### Processing

1. Reversing each string:
   ```
   ["olleH", "dlroW"]
   ["erihsporhS", "yratoN"]
   ```

2. Concatenating with space:
   ```
   "olleH dlroW"
   "erihsporhS yratoN"
   ```

3. Calculating final width:
   - Longest line: `"erihsporhS yratoN"` → 18 characters
   - Total width: 18 (text) + 2×borderWidth = 22

4. Applying border width of 2:
   ```
   **********************
   **********************
   **olleH dlroW       **
   **erihsporhS yratoN **
   **********************
   **********************
   ```

### Output

```plaintext
**********************
**********************
**olleH dlroW       **
**erihsporhS yratoN **
**********************
**********************
```

---

## ✅ Final Notes

- Ensure that **all lines** are padded to the **same length** before adding the border.
- The **top and bottom borders** should contain rows of asterisks repeated for the given `borderWidth`.
- The **left and right borders** should be exactly `borderWidth` asterisks wide.

---

Happy coding and may your stamp always be quirky! 🖋️
