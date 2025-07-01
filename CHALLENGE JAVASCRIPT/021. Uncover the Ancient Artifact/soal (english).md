# 🏺 Uncover the Ancient Artifact

## 📜 Challenge Description

🔍 An archaeologist has uncovered a mysterious artifact covered in strange inscriptions. Your mission is to simulate the delicate process of uncovering and analyzing its hidden structure using programming logic.

---

## 🧠 Objective

Create a function named `uncoverArtifact` that receives one parameter: a string representing a jumbled artifact. The function will process the string using two simulated steps:

1. **Careful Cleaning** — Sort the first half of the string in ascending order.
2. **Revealing Secrets** — Reverse the second half of the string.

Finally, the function joins both parts and returns the "uncovered" version of the artifact.

---

## 🔧 Instructions

### Function Signature:

```js
function uncoverArtifact(artifact: string): string
```

### Parameters:

| Name       | Type     | Description                                                        |
| ---------- | -------- | ------------------------------------------------------------------ |
| `artifact` | `string` | A string of letters and numbers representing the mysterious object |

### Returns:

* `string`: the cleaned and decoded version of the artifact

---

## 📊 Behavior Breakdown

| Step       | Operation                         | Example                      |
| ---------- | --------------------------------- | ---------------------------- |
| 1. Split   | Separate into first & second half | "421olleh" → "421" + "olleh" |
| 2. Sort    | Sort first half ascending         | "421" → "124"                |
| 3. Reverse | Reverse second half               | "olleh" → "hello"            |
| 4. Join    | Merge both results                | "124" + "hello" → "124ehllo" |

---

## 🧪 Example

```js
uncoverArtifact("421olleh");
// Output: "124ehllo"
```

---

## 💡 Sample Visualization

```txt
Initial String:  "421olleh"
                 └───┬───┘
               First | Second
               Half  | Half

After Sort:    "124"
After Reverse: "hello"
Result:        "124ehllo"
```

---

## 🔓 Hints

* Use `slice()` and `split()` to extract and manipulate string parts.
* Sorting can be done using `Array.prototype.sort()`.
* Reverse with `Array.prototype.reverse()`.
* Use `Math.floor()` to handle odd-length strings.


---

## 📝 Notes

* This exercise helps reinforce string manipulation, array methods, and problem decomposition.
* This type of problem is common in coding interviews and puzzles.

---
