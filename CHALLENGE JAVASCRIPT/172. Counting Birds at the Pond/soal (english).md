# 🦆 Counting Birds at the Pond

## 📊 Challenge Overview

**Difficulty Level:** `Beginner` 🟢

---

## 🎯 Objective

A poet is observing birds at a local pond. Every time a bird lands on the pond, the poet notes down its name. Your task is to help the poet count how many times each type of bird has been observed.

---

## 📝 Task Description

Create a function named **`countBirds`** that processes pond observations and returns a count of each bird type.

### Function Signature

```javascript
function countBirds(pondObservations) {
  // Your code here
}
```

---

## 🔧 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `pondObservations` | `array` | An array of strings where each string represents a bird observed at the pond |

### Example Input:
```javascript
['duck', 'swan', 'duck', 'goose']
```

---

## 📤 Return Value

The function should return an **object** where:
- **Keys** are bird names (string)
- **Values** are the count of observations for that bird (number)

### Example Output:
```javascript
{ duck: 3, swan: 1, goose: 1 }
```

---

## 💡 Example

### Input:
```javascript
countBirds(['duck', 'swan', 'duck', 'goose', 'duck'])
```

### Output:
```javascript
{
  duck: 3,
  swan: 1,
  goose: 1
}
```

---

## ⚡ Requirements

- ✅ Solution should be **concise** and **efficient**
- ✅ Ideally between **1 to 9 lines of code**
- ✅ Handle any number of bird observations
- ✅ Handle any bird names

---

## 🎓 Hints

<details>
<summary>Click to reveal hints</summary>

1. Consider using an object to store bird counts
2. Iterate through the array and update counts
3. Think about how to handle birds that haven't been seen before
4. Modern JavaScript methods like `reduce()` can make this very concise

</details>

---

## 🏁 Getting Started

Ready to help the poet? Start coding your solution now!

```javascript
function countBirds(pondObservations) {
  // Write your solution here
}

// Test your function
console.log(countBirds(['duck', 'swan', 'duck', 'goose', 'duck']));
// Expected: { duck: 3, swan: 1, goose: 1 }
```

---

**Happy Coding!** 🚀
