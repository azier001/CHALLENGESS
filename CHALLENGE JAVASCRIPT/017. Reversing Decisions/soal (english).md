# 🌀 Reversing Decisions

**Difficulty:** Easy  
**Category:** String Manipulation  
**Language:** JavaScript

---

## 📚 Overview

This challenge simulates the process of **reconsidering a hasty decision**. By reversing each word in the sentence—while keeping the order of words the same—we represent the introspective act of looking back and reflecting on our choices.

---

## 🎯 Objective

Create a function called `reverseDecision` that processes a given sentence (`decision`) by reversing each word individually while **preserving the original word order**.

---

## 📥 Parameters

| Parameter | Type   | Description                                                                 |
|-----------|--------|-----------------------------------------------------------------------------|
| decision  | string | A sentence consisting of words made up only of alphabetic characters and spaces. No punctuation, no extra spaces. |

---

## 📤 Return

Returns a **string** where **each word is reversed**, but the **word order remains unchanged**.

---

## 🔍 Example

```js
reverseDecision("Think before you act");
```

➡️ Output:
```
"knihT erofeb uoy tca"
```

---

## 🔧 Instructions

1. Split the `decision` string into individual words.
2. Reverse the characters in each word.
3. Join the reversed words back with spaces.
4. Return the final transformed string.

---

## 🧠 Constraints

- The input string only contains:
  - Alphabetic characters (`a-z`, `A-Z`)
  - Single spaces between words
- No punctuation
- No multiple, leading, or trailing spaces

---

## 💡 Hints

- Use `.split(" ")` to separate words.
- Use `.split("").reverse().join("")` to reverse a word.
- Combine everything with `.join(" ")`.

---



---

## ✅ Test Cases

| Input                         | Output                        |
|------------------------------|-------------------------------|
| `"Think before you act"`     | `"knihT erofeb uoy tca"`      |
| `"Regret nothing"`           | `"tergeR gnihton"`            |
| `"Live and learn"`           | `"eviL dna nrael"`            |
| `"Just do it"`               | `"tsuJ od ti"`                |
| `"Seize the day"`            | `"ezeiS eht yad"`             |

---

## 🏁 Conclusion

This challenge helps reinforce understanding of **string manipulation**, especially using array methods like `.split()`, `.map()`, `.reverse()`, and `.join()`—tools commonly used in everyday programming tasks. ✨

Happy coding! 🚀
