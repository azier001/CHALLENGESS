# 🍫 Chocolate Shop Tasting Experience

> Simulate a customer's delightful journey through a chocolate shop, starting from their favorite flavor!

---

## 📌 Challenge Overview

**Difficulty**: 🟢 Easy

Create a function named `chocolateTasting` that simulates the tasting experience in a chocolate shop.

---

## 🧠 Logic to Implement

1. 🔍 **Find the index** of the customer's favorite flavor in the `flavors` array.
2. 🍽️ **Create a new array** that includes all flavors starting from the favorite one.
3. 🚫 If the favorite flavor is **not found** or is the **last flavor**, include **all flavors**.
4. 🔗 **Join** the flavors with `' and '` as a separator.
5. 💬 **Return a message** that describes the customer's tasting experience.

---

## 🧾 Function Signature

```javascript
function chocolateTasting(flavors: string[], favorite: string): string
```

---

## 📥 Parameters

| Name      | Type     | Description                                                  |
|-----------|----------|--------------------------------------------------------------|
| `flavors` | `array`  | An array of strings representing available chocolate flavors |
| `favorite`| `string` | The customer's favorite chocolate flavor                     |

---

## 📤 Returns

- A `string` describing the customer's tasting experience.

---

## 💡 Example

```javascript
const flavors = ['hazelnut', 'caramel', 'mint', 'dark', 'milk'];
const favorite = 'mint';

console.log(chocolateTasting(flavors, favorite));
// Output:
// "The customer's favorite flavor is mint. They tasted: mint and dark and milk"
```

---

## ✅ Expected Output Format

```
"The customer's favorite flavor is <favorite>. They tasted: <flavor1> and <flavor2> and ..."
```

Enjoy coding and chocolate tasting! 🍬
