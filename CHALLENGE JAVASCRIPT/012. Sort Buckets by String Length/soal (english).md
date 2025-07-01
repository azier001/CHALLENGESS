
# 🪣 Sort Buckets by String Length

## 🎯 Challenge

**Difficulty: Easy**

Create a function named `sortBuckets` that receives an array of strings called `buckets`.

### 🎯 Goal:
Sort the array based on the length of each string **in ascending order**, while **preserving the original order** of strings that have the same length.

---

## 🧪 Example

```javascript
sortBuckets(["apple", "orange", "kiwi", "banana"])
// Output: ["kiwi", "apple", "orange", "banana"]
```

> `kiwi` (4 letters), `apple` (5 letters), `orange` (6 letters), `banana` (6 letters)  
> `orange` remains before `banana` because it appears earlier in the original array.

---

## 🧠 Tips

- Use a **stable sort** to maintain the order of strings with the same length.
- JavaScript's `sort` function is stable (since ECMAScript 2019).
- Example:
  ```javascript
  buckets.sort((a, b) => a.length - b.length);
  ```

---

## 📦 Function Signature

```javascript
function sortBuckets(buckets) {
  return buckets.sort((a, b) => a.length - b.length);
}
```

---

## 🚀 Extra Challenge (Optional)

Try writing the function without mutating the original array by using methods like `slice()` to create a copy before sorting.

---

Happy coding! 💡
