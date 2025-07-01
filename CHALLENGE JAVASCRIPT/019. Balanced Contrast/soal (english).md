# ⚖️ Balanced Contrast Function

## 📘 Challenge Description

**Difficulty**: Medium

Create a function named `balancedContrast` that receives three parameters: `arr`, `condition`, and `str`.

This function manipulates the given array and string to create a **balanced contrast** based on certain conditions.

---

## 🔢 Array Manipulation

* If an element is **greater than `condition`**, reverse its position in the array.
* If an element is **less than or equal to `condition`**, keep its position unchanged.

> Example: if `arr = [5, 10, 3, 12]` and `condition = 5`, only `10` and `12` will be reversed in position.

---

## 🔠 String Manipulation

1. Reverse the entire string.
2. For each character in the **original** string:

   * If the character is in the first half of the alphabet (`'a'` to `'m'`), convert the corresponding character in the **reversed** string to **uppercase**.
   * If the character is in the second half of the alphabet (`'n'` to `'z'`), convert the corresponding character in the **reversed** string to **lowercase**.

> This creates visual contrast based on character position in the alphabet.

---

## 📥 Parameters

| Name        | Type       | Description                                                |
| ----------- | ---------- | ---------------------------------------------------------- |
| `arr`       | `number[]` | An array of numbers to manipulate                          |
| `condition` | `number`   | The threshold value for deciding which elements to reverse |
| `str`       | `string`   | A lowercase string (may include spaces) to be processed    |

---

## 📤 Returns

An **object** with two properties:

```js
{
  array: [...],   // The manipulated array
  string: "..."   // The manipulated string
}
```

---

## 🧪 Example

Input:

```js
arr = [5, 10, 3, 12]
condition = 5
str = "hello world"
```

Expected Output:

```js
{
  array: [5, 12, 3, 10],
  string: "dLROw oLLEH"
}
```

---

## 🧠 Tips

* You may use array methods like `.filter()`, `.map()`, and `.reverse()`.
* For strings, consider using `.split('')`, `.toUpperCase()`, `.toLowerCase()`.
* Pay attention to matching character positions between the original and reversed strings.

> 🧩 Use this challenge to sharpen your skills in **array transformation**, **string logic**, and **position-based mapping**.

---


