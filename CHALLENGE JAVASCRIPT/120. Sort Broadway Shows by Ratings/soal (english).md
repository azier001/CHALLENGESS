# 🎭 Broadway Shows Sorting Challenge

## 📊 Difficulty Level
**Easy** ⭐

---

## 🎯 Challenge Overview

Create a function named `sortBroadwayShows` that helps a novice actor prioritize their auditions by sorting Broadway shows based on their popularity ratings.

### 🎪 Scenario
*Imagine you're a budding Broadway star trying to decide which shows to audition for. You want to prioritize the most popular shows to maximize your chances of landing a role in a successful production!*

---

## 📝 Function Requirements

### Function Signature
```javascript
function sortBroadwayShows(showTitles, ratings)
```

### 📥 Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `showTitles` | `Array<string>` | An array of strings representing the titles of Broadway shows |
| `ratings` | `Array<number>` | An array of numbers representing the ratings of the corresponding shows in the same order as `showTitles` |

### 📤 Return Value
- **Type:** `Array<string>`
- **Description:** An array of show titles sorted by their ratings in **descending order** (highest rated first)

---

## 🛠️ Implementation Steps

Follow these steps to solve the challenge:

1. **📋 Create Data Structure**
   - Create an array of objects where each object contains:
     - Show title
     - Corresponding rating

2. **🔄 Sort the Data**
   - Sort the array of objects based on ratings in **descending order**
   - Higher ratings should appear first

3. **🎯 Extract Results**
   - Extract the sorted show titles from the sorted array of objects

4. **✅ Return**
   - Return the array of sorted show titles

---

## 📋 Assumptions & Constraints

> ⚠️ **Important Notes:**
> - The input arrays `showTitles` and `ratings` will always have the **same length**
> - Both arrays will contain **at least one element**
> - All ratings will be **positive numbers**
> - Array indices correspond between `showTitles` and `ratings`

---

## 💡 Example Visualization

```
Input:
showTitles = ["Hamilton", "Cats", "The Lion King", "Phantom"]
ratings    = [9.5, 7.2, 8.8, 9.1]

Process:
[
  { title: "Hamilton", rating: 9.5 },
  { title: "Cats", rating: 7.2 },
  { title: "The Lion King", rating: 8.8 },
  { title: "Phantom", rating: 9.1 }
]
↓ Sort by rating (descending)
[
  { title: "Hamilton", rating: 9.5 },
  { title: "Phantom", rating: 9.1 },
  { title: "The Lion King", rating: 8.8 },
  { title: "Cats", rating: 7.2 }
]

Output:
["Hamilton", "Phantom", "The Lion King", "Cats"]
```

---

## 🎪 Fun Fact
*Broadway shows are rated by audiences and critics, and these ratings often influence ticket sales and the longevity of a show's run. Popular shows like Hamilton and The Lion King have consistently high ratings and have been running for years!*

---

## 🚀 Ready to Code?
Now it's time to implement your `sortBroadwayShows` function and help that aspiring actor make the best audition choices! 🎭✨
